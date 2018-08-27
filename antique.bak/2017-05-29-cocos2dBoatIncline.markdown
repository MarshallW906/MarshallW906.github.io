这学期的一次cocos2d-x作业，其中一部分是要完成一个船体受重不均而发生倾斜、和游戏结束（倾斜角度过大）翻船沉没的效果。谷歌了一番并没有找到相关的标准做法（可能是英文不行），于是自己想了一下。想到了之后发现其实很简单。一行代码就可以搞定。

作业给了个提示是用Rotate。

最开始的想法是，利用contactBegan碰撞检测和updateShip实时手动计算船体与箱子、player的碰撞，但是感觉有点复杂，就暂时搁置了这个想法。 作业要求里给了个提示，Rotate。 查了一下，cocos2d的物理引擎，旋转都是绕锚点进行的。那么只要能固定住船的位置，然后把锚点定在船体中央，剩下的事情交给物理引擎去做就好。

代码很简单。

首先把设置静态取消掉。然后关闭船的重力

```cpp
shipbody->setDynamic(true);

shipbody->setGravityEnable(false);
```

然后设置锚点、固定位置。 我们知道cocos2d-x的锚点默认就是(0.5, 0.5)，也就是物体的几何中心，那么 一行代码解决问题： 在updateShip(float dt)函数里面再加一句固定位置即可。别忘了注册调度器。


```
void FriendShip::updateShip(float dt) {
    /**
     * 把 shipbody->setDynamic(true)
     * 把锚点定为中心
     * 最后再把位置始终保持在同一个地方即可。。。
     */
    ship->setPosition(visibleSize.width / 2, 110);

    if (ship->getRotation() > 60 || ship->getRotation() < -60) {
        ship->getPhysicsBody()->setAngularVelocity(ship->getPhysicsBody()->getAngularVelocity() * 3);
        GameOver();
    }
    return;
}
```

完整的函数多了游戏结束的逻辑判断。翻船的效果其实也随之完成了：游戏结束的时候，取消掉了对该调度器的调用，于是船的位置就不再固定，视觉效果就是船直接沉入海底。
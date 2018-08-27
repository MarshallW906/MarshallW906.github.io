最近刚开始涉足iOS开发，用到了OpenCV。一个经典的问题是Mat与UIImage的互转。
我当时的任务是读取一段视频并提取出每一帧，并且需要显示出来。
官方文档里给出了转换用的函数，尝试发现转换之后的UIImage无法在ImageView中显示，无用。

后来发现，从OpenCV2.4.6开始，官方就直接提供了用于转换的API。

```cpp
#include <opencv2/highgui/ios.h> // OpenCV2
#include <opencv2/imgcodecs/ios.h> // OpenCV3
```

然后就可以用下面的函数进行互转。

```cpp
UIImage* MatToUIImage(const cv::Mat& image);
void UIImageToMat(const UIImage* image, cv::Mat& m, bool alphaExist = false);
```

思考了一下，官方文档里给出的函数可能是用于原始UIImage转至Mat再转回去。此点未确认，如有错误请不吝指教。
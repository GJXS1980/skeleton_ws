
opencv4.0.0版本中，调用imshow函数，报cv::exception错误,imshow函数本身有bug，这个bug在4.0.1版本之后，已经被解决。

sift的使用问题
sift算法，是有专利的，因此在不同的opencv版本中使用的方式不一样，
在3.4.0版本之前，是直接可用的，具体请浏览opencv的帮助手册
在3.4.0 到 4.4.0版本（不包括4.4.0），由于sift申请了专利，因此都被移入到了nonfree文件夹中，需要在cmake的时候，勾选上ENABLE_NONFREE,来获取，大家从网上搜到的大部分代码，凡是#include了一些nonfree里的文件，基本上就是使用这些版本的opencv
opencv在4.4.0及之后的版本里，又重新加入了sift算法，只需要包含features2d.hpp文件即可，且以cv::SIFT来使用即可（使用方法跟之前不一样了），可以在商业软件里使用了
# BmpToArray
Convert BMP images to arrays

# 功能及目的
- 参考其他图片取模软件，解决每次要手动选取图片去获取数据，这样很麻烦。
- 希望做成将图片放进一个路径，让其把该路径的所有BMP转化成数组，并合并在成一个.C文件。
- 数组名就根据图片名称

# 原理
假设一个单色图片的一个像素点对应一个bit，有颜色为1，无颜色为0，例如以下：
```
0001111000
0001111000
0001111000
0001111000
0001111000
0001111000
0001111000
0001111000
```

为一个 10X8 像素的BMP图片，则取出来的数据应该是

```
uint8_t BMP_8X10[] = {
    0x1E, 0x00,
    0x1E, 0x00,
    0x1E, 0x00,
    0x1E, 0x00,
    0x1E, 0x00,
    0x1E, 0x00,
    0x1E, 0x00,
    0x1E, 0x00,
};
```

注意，8个像素点为1byte,如果不满8个点，后面补0到8个点处理，如 00110011 011  => 0x33, 0x30

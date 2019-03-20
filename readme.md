HW03
===
This is the hw03 sample. Please follow the steps below.

# Build the Sample Program

1. Fork this repo to your own github account.

2. Clone the repo that you just forked.

3. Under the hw03 dir, use:

	* `make` to build.

	* `make clean` to clean the ouput files.

4. Extract `gnu-mcu-eclipse-qemu.zip` into hw03 dir. Under the path of hw03, start emulation with `make qemu`.

	See [Lecture 02 ─ Emulation with QEMU] for more details.

5. The sample is a minimal program for ARM Cortex-M4 devices, which enters `while(1);` after reset. Use gdb to get more details.

	See [ESEmbedded_HW02_Example] for knowing how to do the observation and how to use markdown for taking notes.

# Build Your Own Program

1. Edit main.c.

2. Make and run like the steps above.

3. Please avoid using hardware dependent C Standard library functions like `printf`, `malloc`, etc.

# HW03 Requirements

1. How do C functions pass and return parameters? Please describe the related standard used by the Application Binary Interface (ABI) for the ARM architecture.

2. Modify main.c to observe what you found.

3. You have to state how you designed the observation (code), and how you performed it.

	Just like how you did in HW02.

3. If there are any official data that define the rules, you can also use them as references.

4. Push your repo to your github. (Use .gitignore to exclude the output files like object files or executable files and the qemu bin folder)

[Lecture 02 ─ Emulation with QEMU]: http://www.nc.es.ncku.edu.tw/course/embedded/02/#Emulation-with-QEMU
[ESEmbedded_HW02_Example]: https://github.com/vwxyzjimmy/ESEmbedded_HW02_Example

--------------------

- [] **If you volunteer to give the presentation next week, check this.**

--------------------

**★★★ Please take your note here ★★★**
1. 實驗目的
觀察Ｃ語言在組語中如何運作
2. 實驗步驟
設計簡易Ｃ語言
![image](https://github.com/MingChang0329/ESEmbedded_HW03/blob/master/Image/螢幕快照%202019-03-18%20下午7.05.22.png)
將main.c編譯並用qemu進行模擬
![iamge](https://github.com/MingChang0329/ESEmbedded_HW03/blob/master/Image/螢幕快照%202019-03-19%20下午8.41.30.png)
觀察到組語先將3存入r3暫存器中
![image](https://github.com/MingChang0329/ESEmbedded_HW03/blob/master/Image/螢幕快照%202019-03-19%20下午8.42.01.png)
接著運用r7暫存器存入r3的值,再丟入r0中
![image](https://github.com/MingChang0329/ESEmbedded_HW03/blob/master/Image/螢幕快照%202019-03-19%20下午8.42.36.png)
同樣做法丟值進r1和r2
![image](https://github.com/MingChang0329/ESEmbedded_HW03/blob/master/Image/螢幕快照%202019-03-20%20上午10.06.55.png)
將r3的值加上暫存在r7的3
![image](https://github.com/MingChang0329/ESEmbedded_HW03/blob/master/Image/螢幕快照%202019-03-20%20上午10.06.55.png)
最後將r3值存入r0
![image](https://github.com/MingChang0329/ESEmbedded_HW03/blob/master/Image/螢幕快照%202019-03-20%20上午10.07.22.png)
3. 結果與討論
C語言在組語中運作方式基本上跟著已經寫好的ARM架構跑。



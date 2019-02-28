---
title: Вызов неуправляемого кода (P/Invoke)
description: Сведения о вызове собственных функций с помощью P/Invoke в .NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 51026eab92ae4fd47ccdd78321be21bdbb5ecf49
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981261"
---
# <a name="platform-invoke-pinvoke"></a>Вызов неуправляемого кода (P/Invoke)

P/Invoke — это технология, которая позволяет обращаться к структурам, обратным вызовам и функциям в неуправляемых библиотеках из управляемого кода. Большинство API P/Invoke содержится в двух пространствах имен: `System` и `System.Runtime.InteropServices`. Эти пространства имен предоставляют средства для описания способа взаимодействия с собственным компонентом.

Давайте начнем с наиболее общего примера — вызова неуправляемых функций в управляемом коде. Приведем окно сообщения из приложения командной строки:

```csharp
using System.Runtime.InteropServices;

public class Program {

    // Import user32.dll (containing the function we need) and define
    // the method corresponding to the native function.
    [DllImport("user32.dll")]
    public static extern int MessageBox(IntPtr hWnd, String text, String caption, int options);

    public static void Main(string[] args) {
        // Invoke the function as a regular managed method.
        MessageBox(IntPtr.Zero, "Command-line message box", "Attention!", 0);
    }
}
```

Предыдущий пример достаточно прост, но он показывает, что именно нужно для вызова неуправляемых функций из управляемого кода. Рассмотрим пример подробнее:

*   Строка 1 показывает инструкцию using для пространства имен `System.Runtime.InteropServices`, которое содержит все нужные нам элементы.
*   Строка 7 вводит атрибут `DllImport`. Этот атрибут является критически важным, так как он сообщает среде выполнения, что требуется загрузить неуправляемую библиотеку DLL. Передаваемая строка — это библиотека DLL, в которой находится наша целевая функция.
*   Строка 8 является основополагающей для работы P/Invoke. Она определяет управляемый метод, имеющий **точно такую же сигнатуру**, что и неуправляемый. Объявление содержит новое ключевое слово `extern`, которое сообщает среде выполнения, что это внешний метод и что при его вызове среда выполнения должна найти его в библиотеке DLL, указанной в атрибуте `DllImport`.

Остальная часть примера представляет собой обычный вызов метода, аналогичный любому другому управляемому методу.

Для macOS используется аналогичный код. Имя библиотеки в атрибуте `DllImport` необходимо изменить, так как macOS имеет другую схему именования динамических библиотек. В следующем примере используется функция `getpid(2)`, чтобы получить идентификатор процесса приложения и вывести его на консоль.

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libSystem shared library and define the method corresponding to the native function.
        [DllImport("libSystem.dylib")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

В Linux это осуществляется аналогичным образом. Имя функции такое же, так как `getpid(2)` является стандартным системным вызовом [POSIX](https://en.wikipedia.org/wiki/POSIX).

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc shared library and define the method corresponding to the native function.
        [DllImport("libc.so.6")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

## <a name="invoking-managed-code-from-unmanaged-code"></a>Вызов управляемого кода из неуправляемого кода

Среда выполнения обеспечивает взаимодействие в обоих направлениях, что позволяет вызывать собственные функции обратно в управляемый код с помощью указателей функций. В управляемом коде к указателю функции ближе всего **делегат**, так как он позволяет выполнять обратные вызовы из машинного кода в управляемом коде.

Этот компонент используется по аналогии с описанным ранее собственным процессом. Для заданного обратного вызова определяется делегат с такой же сигнатурой, который передается во внешний метод. Обо всем остальном позаботится среда выполнения.

```csharp
using System;
using System.Runtime.InteropServices;

namespace ConsoleApplication1 {

    class Program {

        // Define a delegate that corresponds to the unmanaged function.
        delegate bool EnumWC(IntPtr hwnd, IntPtr lParam);

        // Import user32.dll (containing the function we need) and define
        // the method corresponding to the native function.
        [DllImport("user32.dll")]
        static extern int EnumWindows(EnumWC lpEnumFunc, IntPtr lParam);

        // Define the implementation of the delegate; here, we simply output the window handle.
        static bool OutputWindow(IntPtr hwnd, IntPtr lParam) {
            Console.WriteLine(hwnd.ToInt64());
            return true;
        }

        static void Main(string[] args) {
            // Invoke the method; note the delegate as a first parameter.
            EnumWindows(OutputWindow, IntPtr.Zero);
        }
    }
}
```

Перед рассмотрением примера следует просмотреть сигнатуры неуправляемых функций, с которыми нам предстоит работать. Функция, которую требуется вызвать для перечисления всех окон, имеет такую сигнатуру: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`

Первый параметр — это обратный вызов. Он имеет следующую сигнатуру: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`

Рассмотрим пример подробнее.

*   Строка 9 определяет делегат, который соответствует сигнатуре обратного вызова из неуправляемого кода. Обратите внимание, как типы LPARAM и HWND представлены с помощью `IntPtr` в управляемом коде.
*   Строки 13 и 14 вводят функцию `EnumWindows` из библиотеки user32.dll.
*   Строки 17—20 реализуют делегат. В этом простом примере мы просто выводим маркер на консоль.
*   Наконец, в строке 24 вызывается внешний метод и передается делегат.

Ниже приведены примеры для Linux и macOS. В них мы используем функцию `ftw`, которую можно найти в библиотеке C `libc`. Эта функция используется для обхода иерархий каталогов и принимает указатель функции в качестве одного из своих параметров. Она имеет следующую сигнатуру: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

            // Define a delegate that has the same signature as the native function.
            delegate int DirClbk(string fName, StatClass stat, int typeFlag);

            // Import the libc and define the method to represent the native function.
            [DllImport("libc.so.6")]
            static extern int ftw(string dirpath, DirClbk cl, int descriptors);

            // Implement the above DirClbk delegate;
            // this one just prints out the filename that is passed to it.
            static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                    Console.WriteLine(fName);
                    return 0;
            }

            public static void Main(string[] args){
                    // Call the native function.
                    // Note the second parameter which represents the delegate (callback).
                    ftw(".", DisplayEntry, 10);
            }
    }

    // The native callback takes a pointer to a struct. The below class
    // represents that struct in managed code. You can find more information
    // about this in the section on marshalling below.
    [StructLayout(LayoutKind.Sequential)]
    public class StatClass {
            public uint DeviceID;
            public uint InodeNumber;
            public uint Mode;
            public uint HardLinks;
            public uint UserID;
            public uint GroupID;
            public uint SpecialDeviceID;
            public ulong Size;
            public ulong BlockSize;
            public uint Blocks;
            public long TimeLastAccess;
            public long TimeLastModification;
            public long TimeLastStatusChange;
    }
}
```

В примере для macOS используется та же функция. Единственное отличие состоит в аргументе для атрибута `DllImport`, так как macOS сохраняет `libc` в другом месте.

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
        public static class Program {

                // Define a delegate that has the same signature as the native function.
                delegate int DirClbk(string fName, StatClass stat, int typeFlag);

                // Import the libc and define the method to represent the native function.
                [DllImport("libSystem.dylib")]
                static extern int ftw(string dirpath, DirClbk cl, int descriptors);

                // Implement the above DirClbk delegate;
                // this one just prints out the filename that is passed to it.
                static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                        Console.WriteLine(fName);
                        return 0;
                }

                public static void Main(string[] args){
                        // Call the native function.
                        // Note the second parameter which represents the delegate (callback).
                        ftw(".", DisplayEntry, 10);
                }
        }

        // The native callback takes a pointer to a struct. The below class
        // represents that struct in managed code.
        [StructLayout(LayoutKind.Sequential)]
        public class StatClass {
                public uint DeviceID;
                public uint InodeNumber;
                public uint Mode;
                public uint HardLinks;
                public uint UserID;
                public uint GroupID;
                public uint SpecialDeviceID;
                public ulong Size;
                public ulong BlockSize;
                public uint Blocks;
                public long TimeLastAccess;
                public long TimeLastModification;
                public long TimeLastStatusChange;
        }
}
```

Оба предыдущих примера зависят от параметров, и в обоих случаях параметры задаются в виде управляемых типов. На другой стороне среда выполнения преобразует их в эквивалентные. См. дополнительные сведения о [маршалировании типов в машинный код](type-marshalling.md).


## <a name="more-resources"></a>Дополнительные ресурсы

*   [Вики-сайт PInvoke.net](https://www.pinvoke.net/) — это отличный ресурс с информацией о распространенных API Win32 и способах их вызова.
*   [Сведения о P/Invoke на сайте MSDN](/cpp/dotnet/native-and-dotnet-interoperability)
*   [Документация Mono по P/Invoke](https://www.mono-project.com/docs/advanced/pinvoke/)

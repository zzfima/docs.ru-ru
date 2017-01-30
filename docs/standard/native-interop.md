---
title: "Взаимодействие на уровне машинного кода"
description: "Взаимодействие на уровне машинного кода"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: ronpet
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3c357112-35fb-44ba-a07b-6a1c140370ac
translationtype: Human Translation
ms.sourcegitcommit: 3aeaba5c8cf800c652941b5e6c2bc9f072849893
ms.openlocfilehash: 36041eda54290484741c375ae776b7bf1a74d7a1

---

# <a name="native-interoperability"></a>Взаимодействие на уровне машинного кода

В этом документе мы немного подробнее рассмотрим все три способа "взаимодействия на уровне машинного кода", доступные на платформе .NET.

Для обращения к машинному коду существует несколько причин:

*   Операционные системы содержат большое количество API, отсутствующих в библиотеках управляемых классов. Ярким примером этого является доступ к функциям управления оборудованием или операционной системой.
*   Взаимодействие с другими компонентами, которые содержат или могут создавать ABI в стиле C (собственные ABI). Сюда относится, например, код Java, предоставляемый через [собственный интерфейс Java (JNI)](http://docs.oracle.com/javase/8/docs/technotes/guides/jni/), или любой другой управляемый язык, который может создать собственный компонент.
*   В Windows основная часть устанавливаемого программного обеспечения, например пакет Microsoft Office, регистрирует COM-компоненты, которые представляют свои программы и позволяют разработчикам автоматизировать или использовать их. Для этого также требуется взаимодействие на уровне машинного кода.

Конечно же, приведенный выше список охватывает не все возможные ситуации и сценарии, в которых разработчику может потребоваться взаимодействовать с собственными компонентами. Например, библиотека классов .NET использует поддержку взаимодействия на уровне машинного кода для реализации значительного количества своих API, таких как поддержка и использование консоли, доступ к файловой системе и др. Следует лишь отметить наличие соответствующей возможности, если она вдруг понадобится.

> [!NOTE]
> Большинство примеров в этом документе приводятся для всех трех поддерживаемых платформ .NET Core (Windows, Linux и macOS). Однако для краткости и наглядности приведен лишь один пример, использующий имена и расширения файлов Windows ("dll" для библиотек). Это сделано исключительно ради удобства и совершенно не означает, что такие функции недоступны в Linux и macOS.

## <a name="platform-invoke-pinvoke"></a>Вызов неуправляемого кода (P/Invoke)

P/Invoke — это технология, которая позволяет обращаться к структурам, обратным вызовам и функциям в неуправляемых библиотеках из управляемого кода. Большинство API P/Invoke содержится в двух пространствах имен: `System` и `System.Runtime.InteropServices`. Эти пространства имен предоставляют доступ к атрибутам, описывающим способ взаимодействия с собственным компонентом.

Давайте начнем с наиболее общего примера — вызова неуправляемых функций в управляемом коде. Приведем окно сообщения из приложения командной строки:

```cs
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

*   Строка 1 показывает инструкцию using для `System.Runtime.InteropServices` — пространства имен, которое содержит все нужные нам элементы.
*   Строка 5 вводит атрибут `DllImport`. Этот атрибут является критически важным, так как он сообщает среде выполнения, что требуется загрузить неуправляемую библиотеку DLL. Это библиотека DLL, которую нужно вызвать.
*   Строка 6 является основополагающей для работы P/Invoke. Она определяет управляемый метод, имеющий **точно такую же сигнатуру**, что и неуправляемый. Объявление содержит новое ключевое слово `extern`, которое сообщает среде выполнения, что это внешний метод и что при его вызове среда выполнения должна найти его в библиотеке DLL, указанной в атрибуте `DllImport`.

Остальная часть примера представляет собой обычный вызов метода, аналогичный любому другому управляемому методу.

Для macOS используется аналогичный код. Единственное, что требуется изменить, это имя библиотеки в атрибуте `DllImport`, так как macOS имеет другую схему именования динамических библиотек. Приведенный ниже пример использует функцию `getpid(2)`, чтобы получить идентификатор процесса приложения и вывести его на консоль.

```cs
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc and define the method corresponding to the native function.
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

В Linux это осуществляется аналогично. Имя функции такое же, так как `getpid(2)` является системным вызовом [POSIX](https://en.wikipedia.org/wiki/POSIX).

```cs
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc and define the method corresponding to the native function.
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

### <a name="invoking-managed-code-from-unmanaged-code"></a>Вызов управляемого кода из неуправляемого кода

Конечно же, среда выполнения обеспечивает взаимодействие в обоих направлениях, что позволяет вызывать управляемые артефакты из собственных функций с помощью указателей функций. В управляемом коде к указателю функции ближе всего **делегат**, так как он позволяет выполнять обратные вызовы из машинного кода в управляемом коде.

Данный компонент используется по аналогии с описанным выше собственным процессом. Для заданного обратного вызова определяется делегат с такой же сигнатурой, который передается во внешний метод. Обо всем остальном позаботится среда выполнения.

```cs
using System;
using System.Runtime.InteropServices;

namespace ConsoleApplication1 {

    class Program {

        // Define a delegate that corresponds to the unmanaged function.
        delegate bool EnumWC(IntPtr hwnd, IntPtr lParam);

        // Import user32.dll (containing the function we need) and define
        // the method corresponding to the native function.
        [DllImport("user32.dll")]
        static extern int EnumWindows(EnumWC hWnd, IntPtr lParam);

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

Перед рассмотрением примера следует упомянуть сигнатуры неуправляемых функций, с которыми нам предстоит работать. Функция, которую требуется вызвать для перечисления всех окон, имеет следующую сигнатуру: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`

Первый параметр — это обратный вызов. Он имеет следующую сигнатуру: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`

Учитывая это, рассмотрим пример:

*   Строка 8 определяет делегат, который соответствует сигнатуре обратного вызова из неуправляемого кода. Обратите внимание, как типы LPARAM и HWND представлены с помощью `IntPtr` в управляемом коде.
*   Строки 10 и 11 вводят функцию `EnumWindows` из библиотеки user32.dll.
*   Строки 13–16 реализуют делегат. В этом простом примере мы просто выводим маркер на консоль.
*   Наконец, в строке 19 мы вызываем внешний метод и передаем делегат.

Ниже приведены примеры для Linux и macOS. В них мы используем функцию `ftw`, которую можно найти в библиотеке C `libc`. Эта функция используется для обхода иерархий каталогов и принимает указатель функции в качестве одного из своих параметров. Она имеет следующую сигнатуру: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.

```cs
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

```cs
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

Оба приведенных выше примера зависят от параметров, и в обоих случаях параметры задаются в виде управляемых типов. На другой стороне среда выполнения преобразует их в эквивалентные. Поскольку этот процесс очень важен для написания качественного кода взаимодействия на уровне машинного кода, давайте рассмотрим, что происходит, когда среда выполнения производит _маршалинг_ типов.

## <a name="type-marshalling"></a>Маршалинг типов

**Маршалинг** — это процесс преобразования типов, когда им требуется перейти из управляемого кода в машинный и наоборот.

Необходимость в маршалинге вызвана тем, что типы в управляемом и неуправляемом коде различаются. Например, в управляемом коде имеется `String`, а в неуправляемом строки могут иметь различный формат: Юникод, отличный от Юникода, с конечным символом NULL, ASCII и т. д. По умолчанию подсистема P/Invoke пытается выбрать правильное решение на основе поведения по умолчанию, о чем можно узнать на сайте [MSDN](https://msdn.microsoft.com/library/zah6xy75.aspx). Однако в ситуациях, когда требуется дополнительный контроль, можно применить атрибут `MarshalAs`, чтобы указать ожидаемый тип на стороне неуправляемого кода. Например, если строка должна передаваться в виде строки ANSI с конечным символом NULL, это можно сделать следующим образом:

```cs
[DllImport("somenativelibrary.dll"]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr) string parameter);

```

### <a name="marshalling-classes-and-structs"></a>Маршалинг классов и структур

Другим аспектом маршалинга типов является способ передачи структуры в неуправляемый метод. Например, некоторые неуправляемые методы требуют указания структуры в качестве параметра. В таких случаях требуется создать соответствующую структуру или соответствующий класс в управляемом коде для использования в качестве параметра. Однако простого определения класса недостаточно. Нужно также сообщить маршалеру, как сопоставлять поля класса с неуправляемой структурой. Именно для этого и используется атрибут `StructLayout`.

```cs
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}

```

Выше приведен простой пример вызова функции `GetSystemTime()`. Интерес представляет строка 4\.. Атрибут указывает, что поля класса должны последовательно сопоставляться со структурой на другой (неуправляемой) стороне. Это означает, что имена полей не важны, важен только их порядок, так как он должен соответствовать следующей неуправляемой структуре:

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME*;

```

Мы уже видели подобный подход для Linux и macOS в предыдущем примере. Ниже он повторяется снова.

```cs
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

```

Класс `StatClass` представляет структуру, возвращаемую системным вызовом `stat` в системах UNIX. Он представляет сведения о заданном файле. Приведенный выше класс является представлением структуры stat в управляемом коде. Еще раз отметим, что поля в классе обязательно должны находиться в том же порядке, что в собственной структуре (их можно найти, внимательно изучив страницы справки по выбранной реализации UNIX), и иметь тот же тип.

## <a name="more-resources"></a>Дополнительные ресурсы

*   [Вики-сайт PInvoke.net](http://www.pinvoke.net) — это отличный ресурс с информацией о распространенных API Win32 и способах их вызова.
*   [Сведения о P/Invoke на сайте MSDN](https://msdn.microsoft.com/library/zbz07712.aspx)
*   [Документация Mono по P/Invoke](http://www.mono-project.com/docs/advanced/pinvoke/)



<!--HONumber=Nov16_HO3-->



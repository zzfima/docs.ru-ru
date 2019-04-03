---
title: Вызов неуправляемого кода (P/Invoke)
description: Сведения о вызове собственных функций с помощью P/Invoke в .NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 4836096e12f6c3d317daa5da91566ab472053ede
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409241"
---
# <a name="platform-invoke-pinvoke"></a><span data-ttu-id="e0cf5-103">Вызов неуправляемого кода (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="e0cf5-103">Platform Invoke (P/Invoke)</span></span>

<span data-ttu-id="e0cf5-104">P/Invoke — это технология, которая позволяет обращаться к структурам, обратным вызовам и функциям в неуправляемых библиотеках из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-104">P/Invoke is a technology that allows you to access structs, callbacks, and functions in unmanaged libraries from your managed code.</span></span> <span data-ttu-id="e0cf5-105">Большинство API P/Invoke содержится в двух пространствах имен: `System` и `System.Runtime.InteropServices`.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-105">Most of the P/Invoke API is contained in two namespaces: `System` and `System.Runtime.InteropServices`.</span></span> <span data-ttu-id="e0cf5-106">Эти пространства имен предоставляют средства для описания способа взаимодействия с собственным компонентом.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-106">Using these two namespaces give you the tools to describe how you want to communicate with the native component.</span></span>

<span data-ttu-id="e0cf5-107">Давайте начнем с наиболее общего примера — вызова неуправляемых функций в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-107">Let’s start from the most common example, and that is calling unmanaged functions in your managed code.</span></span> <span data-ttu-id="e0cf5-108">Приведем окно сообщения из приложения командной строки:</span><span class="sxs-lookup"><span data-stu-id="e0cf5-108">Let’s show a message box from a command-line application:</span></span>

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

<span data-ttu-id="e0cf5-109">Предыдущий пример достаточно прост, но он показывает, что именно нужно для вызова неуправляемых функций из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-109">The previous example is simple, but it does show off what's needed to invoke unmanaged functions from managed code.</span></span> <span data-ttu-id="e0cf5-110">Рассмотрим пример подробнее:</span><span class="sxs-lookup"><span data-stu-id="e0cf5-110">Let’s step through the example:</span></span>

*   <span data-ttu-id="e0cf5-111">Строка 1 показывает инструкцию using для пространства имен `System.Runtime.InteropServices`, которое содержит все нужные нам элементы.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-111">Line #1 shows the using statement for the `System.Runtime.InteropServices` namespace that holds all the items needed.</span></span>
*   <span data-ttu-id="e0cf5-112">Строка 7 вводит атрибут `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-112">Line #7 introduces the `DllImport` attribute.</span></span> <span data-ttu-id="e0cf5-113">Этот атрибут является критически важным, так как он сообщает среде выполнения, что требуется загрузить неуправляемую библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-113">This attribute is crucial, as it tells the runtime that it should load the unmanaged DLL.</span></span> <span data-ttu-id="e0cf5-114">Передаваемая строка — это библиотека DLL, в которой находится наша целевая функция.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-114">The string passed in is the DLL our target function is in.</span></span>
*   <span data-ttu-id="e0cf5-115">Строка 8 является основополагающей для работы P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-115">Line #8 is the crux of the P/Invoke work.</span></span> <span data-ttu-id="e0cf5-116">Она определяет управляемый метод, имеющий **точно такую же сигнатуру**, что и неуправляемый.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-116">It defines a managed method that has the **exact same signature** as the unmanaged one.</span></span> <span data-ttu-id="e0cf5-117">Объявление содержит новое ключевое слово `extern`, которое сообщает среде выполнения, что это внешний метод и что при его вызове среда выполнения должна найти его в библиотеке DLL, указанной в атрибуте `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-117">The declaration has a new keyword that you can notice, `extern`, which tells the runtime this is an external method, and that when you invoke it, the runtime should find it in the DLL specified in `DllImport` attribute.</span></span>

<span data-ttu-id="e0cf5-118">Остальная часть примера представляет собой обычный вызов метода, аналогичный любому другому управляемому методу.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-118">The rest of the example is just invoking the method as you would any other managed method.</span></span>

<span data-ttu-id="e0cf5-119">Для macOS используется аналогичный код.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-119">The sample is similar for macOS.</span></span> <span data-ttu-id="e0cf5-120">Имя библиотеки в атрибуте `DllImport` необходимо изменить, так как macOS имеет другую схему именования динамических библиотек.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-120">The name of the library in the `DllImport` attribute needs to change since macOS has a different scheme of naming dynamic libraries.</span></span> <span data-ttu-id="e0cf5-121">В следующем примере используется функция `getpid(2)`, чтобы получить идентификатор процесса приложения и вывести его на консоль.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-121">The following sample uses the `getpid(2)` function to get the process ID of the application and print it out to the console:</span></span>

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

<span data-ttu-id="e0cf5-122">В Linux это осуществляется аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-122">It is also similar on Linux.</span></span> <span data-ttu-id="e0cf5-123">Имя функции такое же, так как `getpid(2)` является стандартным системным вызовом [POSIX](https://en.wikipedia.org/wiki/POSIX).</span><span class="sxs-lookup"><span data-stu-id="e0cf5-123">The function name is the same, since `getpid(2)` is a standard [POSIX](https://en.wikipedia.org/wiki/POSIX) system call.</span></span>

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

## <a name="invoking-managed-code-from-unmanaged-code"></a><span data-ttu-id="e0cf5-124">Вызов управляемого кода из неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="e0cf5-124">Invoking managed code from unmanaged code</span></span>

<span data-ttu-id="e0cf5-125">Среда выполнения обеспечивает взаимодействие в обоих направлениях, что позволяет вызывать собственные функции обратно в управляемый код с помощью указателей функций.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-125">The runtime allows communication to flow in both directions, enabling you to call back into managed code from native functions by using function pointers.</span></span> <span data-ttu-id="e0cf5-126">В управляемом коде к указателю функции ближе всего **делегат**, так как он позволяет выполнять обратные вызовы из машинного кода в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-126">The closest thing to a function pointer in managed code is a **delegate**, so this is what is used to allow callbacks from native code into managed code.</span></span>

<span data-ttu-id="e0cf5-127">Этот компонент используется по аналогии с описанным ранее собственным процессом.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-127">The way to use this feature is similar to the managed to native process previously described.</span></span> <span data-ttu-id="e0cf5-128">Для заданного обратного вызова определяется делегат с такой же сигнатурой, который передается во внешний метод.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-128">For a given callback, you define a delegate that matches the signature and pass that into the external method.</span></span> <span data-ttu-id="e0cf5-129">Обо всем остальном позаботится среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-129">The runtime will take care of everything else.</span></span>

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

<span data-ttu-id="e0cf5-130">Перед рассмотрением примера следует просмотреть сигнатуры неуправляемых функций, с которыми нам предстоит работать.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-130">Before walking through the example, it's good to review the signatures of the unmanaged functions you need to work with.</span></span> <span data-ttu-id="e0cf5-131">Функция, которую требуется вызвать для перечисления всех окон, имеет такую сигнатуру: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="e0cf5-131">The function to be called to enumerate all of the windows has the following signature: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span></span>

<span data-ttu-id="e0cf5-132">Первый параметр — это обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-132">The first parameter is a callback.</span></span> <span data-ttu-id="e0cf5-133">Он имеет следующую сигнатуру: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="e0cf5-133">The said callback has the following signature: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span></span>

<span data-ttu-id="e0cf5-134">Рассмотрим пример подробнее.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-134">Now, let’s walk through the example:</span></span>

*   <span data-ttu-id="e0cf5-135">Строка 9 определяет делегат, который соответствует сигнатуре обратного вызова из неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-135">Line #9 in the example defines a delegate that matches the signature of the callback from unmanaged code.</span></span> <span data-ttu-id="e0cf5-136">Обратите внимание, как типы LPARAM и HWND представлены с помощью `IntPtr` в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-136">Notice how the LPARAM and HWND types are represented using `IntPtr` in the managed code.</span></span>
*   <span data-ttu-id="e0cf5-137">Строки 13 и 14 вводят функцию `EnumWindows` из библиотеки user32.dll.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-137">Lines #13 and #14 introduce the `EnumWindows` function from the user32.dll library.</span></span>
*   <span data-ttu-id="e0cf5-138">Строки 17—20 реализуют делегат.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-138">Lines #17 - 20 implement the delegate.</span></span> <span data-ttu-id="e0cf5-139">В этом простом примере мы просто выводим маркер на консоль.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-139">For this simple example, we just want to output the handle to the console.</span></span>
*   <span data-ttu-id="e0cf5-140">Наконец, в строке 24 вызывается внешний метод и передается делегат.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-140">Finally, in line #24, the external method is called and passed in the delegate.</span></span>

<span data-ttu-id="e0cf5-141">Ниже приведены примеры для Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-141">The Linux and macOS examples are shown below.</span></span> <span data-ttu-id="e0cf5-142">В них мы используем функцию `ftw`, которую можно найти в библиотеке C `libc`.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-142">For them, we use the `ftw` function that can be found in `libc`, the C library.</span></span> <span data-ttu-id="e0cf5-143">Эта функция используется для обхода иерархий каталогов и принимает указатель функции в качестве одного из своих параметров.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-143">This function is used to traverse directory hierarchies and it takes a pointer to a function as one of its parameters.</span></span> <span data-ttu-id="e0cf5-144">Она имеет следующую сигнатуру: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-144">The said function has the following signature: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span></span>

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

<span data-ttu-id="e0cf5-145">В примере для macOS используется та же функция. Единственное отличие состоит в аргументе для атрибута `DllImport`, так как macOS сохраняет `libc` в другом месте.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-145">macOS example uses the same function, and the only difference is the argument to the `DllImport` attribute, as macOS keeps `libc` in a different place.</span></span>

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

<span data-ttu-id="e0cf5-146">Оба предыдущих примера зависят от параметров, и в обоих случаях параметры задаются в виде управляемых типов.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-146">Both of the previous examples depend on parameters, and in both cases, the parameters are given as managed types.</span></span> <span data-ttu-id="e0cf5-147">На другой стороне среда выполнения преобразует их в эквивалентные.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-147">Runtime does the "right thing" and processes these into its equivalents on the other side.</span></span> <span data-ttu-id="e0cf5-148">См. дополнительные сведения о [маршалировании типов в машинный код](type-marshalling.md).</span><span class="sxs-lookup"><span data-stu-id="e0cf5-148">Learn about how types are marshalled to native code in our page on [Type marshalling](type-marshalling.md).</span></span>


## <a name="more-resources"></a><span data-ttu-id="e0cf5-149">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e0cf5-149">More resources</span></span>

*   <span data-ttu-id="e0cf5-150">[Вики-сайт PInvoke.net](https://www.pinvoke.net/) — это отличный ресурс с информацией о распространенных API Windows и способах их вызова.</span><span class="sxs-lookup"><span data-stu-id="e0cf5-150">[PInvoke.net wiki](https://www.pinvoke.net/) an excellent Wiki with information on common Windows APIs and how to call them.</span></span>
*   [<span data-ttu-id="e0cf5-151">Сведения о P/Invoke на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="e0cf5-151">P/Invoke on MSDN</span></span>](/cpp/dotnet/native-and-dotnet-interoperability)
*   [<span data-ttu-id="e0cf5-152">Документация Mono по P/Invoke</span><span class="sxs-lookup"><span data-stu-id="e0cf5-152">Mono documentation on P/Invoke</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/)

---
title: Взаимодействие на уровне машинного кода
description: Сведения о взаимодействии с компонентами на базе машинного кода в .NET.
author: blackdwarf
ms.author: ronpet
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 3c357112-35fb-44ba-a07b-6a1c140370ac
ms.openlocfilehash: 2f427eb5d8f41f730d4263425e268213db92236d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143192"
---
# <a name="native-interoperability"></a><span data-ttu-id="41220-103">Взаимодействие на уровне машинного кода</span><span class="sxs-lookup"><span data-stu-id="41220-103">Native Interoperability</span></span>

<span data-ttu-id="41220-104">В этом документе мы немного подробнее рассмотрим все три способа "взаимодействия на уровне машинного кода", доступные при использовании .NET.</span><span class="sxs-lookup"><span data-stu-id="41220-104">In this document, we will dive a little bit deeper into all three ways of doing "native interoperability" that are available using .NET.</span></span>

<span data-ttu-id="41220-105">Для обращения к машинному коду существует несколько причин:</span><span class="sxs-lookup"><span data-stu-id="41220-105">There are a few of reasons why you would want to call into native code:</span></span>

*   <span data-ttu-id="41220-106">Операционные системы содержат большое количество API, отсутствующих в библиотеках управляемых классов.</span><span class="sxs-lookup"><span data-stu-id="41220-106">Operating Systems come with a large volume of APIs that are not present in the managed class libraries.</span></span> <span data-ttu-id="41220-107">Ярким примером этого является доступ к функциям управления оборудованием или операционной системой.</span><span class="sxs-lookup"><span data-stu-id="41220-107">A prime example for this would be access to hardware or operating system management functions.</span></span>
*   <span data-ttu-id="41220-108">Взаимодействие с другими компонентами, которые содержат или могут создавать ABI в стиле C (собственные ABI).</span><span class="sxs-lookup"><span data-stu-id="41220-108">Communicating with other components that have or can produce C-style ABIs (native ABIs).</span></span> <span data-ttu-id="41220-109">Сюда относится, например, код Java, предоставляемый через [собственный интерфейс Java (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/), или любой другой управляемый язык, который может создать собственный компонент.</span><span class="sxs-lookup"><span data-stu-id="41220-109">This covers, for example, Java code that is exposed via [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) or any other managed language that could produce a native component.</span></span>
*   <span data-ttu-id="41220-110">В Windows основная часть устанавливаемого программного обеспечения, например пакет Microsoft Office, регистрирует COM-компоненты, которые представляют свои программы и позволяют разработчикам автоматизировать или использовать их.</span><span class="sxs-lookup"><span data-stu-id="41220-110">On Windows, most of the software that gets installed, such as Microsoft Office suite, registers COM components that represent their programs and allow developers to automate them or use them.</span></span> <span data-ttu-id="41220-111">Для этого также требуется взаимодействие на уровне машинного кода.</span><span class="sxs-lookup"><span data-stu-id="41220-111">This also requires native interoperability.</span></span>

<span data-ttu-id="41220-112">Конечно же, приведенный выше список охватывает не все возможные ситуации и сценарии, в которых разработчику может потребоваться взаимодействовать с собственными компонентами.</span><span class="sxs-lookup"><span data-stu-id="41220-112">Of course, the list above does not cover all of the potential situations and scenarios in which the developer would want/like/need to interface with native components.</span></span> <span data-ttu-id="41220-113">Например, библиотека классов .NET использует поддержку взаимодействия на уровне машинного кода для реализации значительного количества своих API, таких как поддержка и использование консоли, доступ к файловой системе и др.</span><span class="sxs-lookup"><span data-stu-id="41220-113">.NET class library, for instance, uses the native interoperability support to implement a fair number of its APIs, like console support and manipulation, file system access and others.</span></span> <span data-ttu-id="41220-114">Следует лишь отметить наличие соответствующей возможности, если она вдруг понадобится.</span><span class="sxs-lookup"><span data-stu-id="41220-114">However, it is important to note that there is an option, should one need it.</span></span>

> [!NOTE]
> <span data-ttu-id="41220-115">Большинство примеров в этом документе приводятся для всех трех поддерживаемых платформ .NET Core (Windows, Linux и macOS).</span><span class="sxs-lookup"><span data-stu-id="41220-115">Most of the examples in this document will be presented for all three supported platforms for .NET Core (Windows, Linux and macOS).</span></span> <span data-ttu-id="41220-116">Но для краткости и наглядности приведен лишь один пример, использующий имена и расширения файлов Windows ("dll" для библиотек).</span><span class="sxs-lookup"><span data-stu-id="41220-116">However, for some short and illustrative examples, just one sample is shown that uses Windows filenames and extensions (that is, "dll" for libraries).</span></span> <span data-ttu-id="41220-117">Это сделано исключительно ради удобства и совершенно не означает, что такие функции недоступны в Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="41220-117">This does not mean that those features are not available on Linux or macOS, it was done merely for convenience sake.</span></span>

## <a name="platform-invoke-pinvoke"></a><span data-ttu-id="41220-118">Вызов неуправляемого кода (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="41220-118">Platform Invoke (P/Invoke)</span></span>

<span data-ttu-id="41220-119">P/Invoke — это технология, которая позволяет обращаться к структурам, обратным вызовам и функциям в неуправляемых библиотеках из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="41220-119">P/Invoke is a technology that allows you to access structs, callbacks and functions in unmanaged libraries from your managed code.</span></span> <span data-ttu-id="41220-120">Большинство API P/Invoke содержится в двух пространствах имен: `System` и `System.Runtime.InteropServices`.</span><span class="sxs-lookup"><span data-stu-id="41220-120">Most of the P/Invoke API is contained in two namespaces: `System` and `System.Runtime.InteropServices`.</span></span> <span data-ttu-id="41220-121">Эти пространства имен предоставляют доступ к атрибутам, описывающим способ взаимодействия с собственным компонентом.</span><span class="sxs-lookup"><span data-stu-id="41220-121">Using these two namespaces will allow you access to the attributes that describe how you want to communicate with the native component.</span></span>

<span data-ttu-id="41220-122">Давайте начнем с наиболее общего примера — вызова неуправляемых функций в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="41220-122">Let’s start from the most common example, and that is calling unmanaged functions in your managed code.</span></span> <span data-ttu-id="41220-123">Приведем окно сообщения из приложения командной строки:</span><span class="sxs-lookup"><span data-stu-id="41220-123">Let’s show a message box from a command-line application:</span></span>

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

<span data-ttu-id="41220-124">Предыдущий пример достаточно прост, но он показывает, что именно нужно для вызова неуправляемых функций из управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="41220-124">The example above is pretty simple, but it does show off what is needed to invoke unmanaged functions from managed code.</span></span> <span data-ttu-id="41220-125">Рассмотрим пример подробнее:</span><span class="sxs-lookup"><span data-stu-id="41220-125">Let’s step through the example:</span></span>

*   <span data-ttu-id="41220-126">Строка 1 показывает инструкцию using для `System.Runtime.InteropServices` — пространства имен, которое содержит все нужные нам элементы.</span><span class="sxs-lookup"><span data-stu-id="41220-126">Line #1 shows the using statement for the `System.Runtime.InteropServices` which is the namespace that holds all of the items we need.</span></span>
*   <span data-ttu-id="41220-127">Строка 5 вводит атрибут `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="41220-127">Line #5 introduces the `DllImport` attribute.</span></span> <span data-ttu-id="41220-128">Этот атрибут является критически важным, так как он сообщает среде выполнения, что требуется загрузить неуправляемую библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="41220-128">This attribute is crucial, as it tells the runtime that it should load the unmanaged DLL.</span></span> <span data-ttu-id="41220-129">Это библиотека DLL, которую нужно вызвать.</span><span class="sxs-lookup"><span data-stu-id="41220-129">This is the DLL into which we wish to invoke.</span></span>
*   <span data-ttu-id="41220-130">Строка 6 является основополагающей для работы P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="41220-130">Line #6 is the crux of the P/Invoke work.</span></span> <span data-ttu-id="41220-131">Она определяет управляемый метод, имеющий **точно такую же сигнатуру**, что и неуправляемый.</span><span class="sxs-lookup"><span data-stu-id="41220-131">It defines a managed method that has the **exact same signature** as the unmanaged one.</span></span> <span data-ttu-id="41220-132">Объявление содержит новое ключевое слово `extern`, которое сообщает среде выполнения, что это внешний метод и что при его вызове среда выполнения должна найти его в библиотеке DLL, указанной в атрибуте `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="41220-132">The declaration has a new keyword that you can notice, `extern`, which tells the runtime this is an external method, and that when you invoke it, the runtime should find it in the DLL specified in `DllImport` attribute.</span></span>

<span data-ttu-id="41220-133">Остальная часть примера представляет собой обычный вызов метода, аналогичный любому другому управляемому методу.</span><span class="sxs-lookup"><span data-stu-id="41220-133">The rest of the example is just invoking the method as you would any other managed method.</span></span>

<span data-ttu-id="41220-134">Для macOS используется аналогичный код.</span><span class="sxs-lookup"><span data-stu-id="41220-134">The sample is similar for macOS.</span></span> <span data-ttu-id="41220-135">Единственное, что требуется изменить, это имя библиотеки в атрибуте `DllImport`, так как macOS имеет другую схему именования динамических библиотек.</span><span class="sxs-lookup"><span data-stu-id="41220-135">One thing that needs to change is, of course, the name of the library in the `DllImport` attribute, as macOS has a different scheme of naming dynamic libraries.</span></span> <span data-ttu-id="41220-136">Приведенный ниже пример использует функцию `getpid(2)`, чтобы получить идентификатор процесса приложения и вывести его на консоль.</span><span class="sxs-lookup"><span data-stu-id="41220-136">The sample below uses the `getpid(2)` function to get the process ID of the application and print it out to the console.</span></span>

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

<span data-ttu-id="41220-137">В Linux это осуществляется аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="41220-137">It is also similar on Linux.</span></span> <span data-ttu-id="41220-138">Имя функции такое же, так как `getpid(2)` является стандартным системным вызовом [POSIX](https://en.wikipedia.org/wiki/POSIX).</span><span class="sxs-lookup"><span data-stu-id="41220-138">The function name is the same, since `getpid(2)` is a standard [POSIX](https://en.wikipedia.org/wiki/POSIX) system call.</span></span>

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

### <a name="invoking-managed-code-from-unmanaged-code"></a><span data-ttu-id="41220-139">Вызов управляемого кода из неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="41220-139">Invoking managed code from unmanaged code</span></span>

<span data-ttu-id="41220-140">Конечно же, среда выполнения обеспечивает взаимодействие в обоих направлениях, что позволяет вызывать управляемые артефакты из собственных функций с помощью указателей функций.</span><span class="sxs-lookup"><span data-stu-id="41220-140">Of course, the runtime allows communication to flow both ways which enables you to call into managed artifacts from native functions, using function pointers.</span></span> <span data-ttu-id="41220-141">В управляемом коде к указателю функции ближе всего **делегат**, так как он позволяет выполнять обратные вызовы из машинного кода в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="41220-141">The closest thing to a function pointer in managed code is a **delegate**, so this is what is used to allow callbacks from native code into managed code.</span></span>

<span data-ttu-id="41220-142">Данный компонент используется по аналогии с описанным выше собственным процессом.</span><span class="sxs-lookup"><span data-stu-id="41220-142">The way to use this feature is similar to managed to native process described above.</span></span> <span data-ttu-id="41220-143">Для заданного обратного вызова определяется делегат с такой же сигнатурой, который передается во внешний метод.</span><span class="sxs-lookup"><span data-stu-id="41220-143">For a given callback, you define a delegate that matches the signature, and pass that into the external method.</span></span> <span data-ttu-id="41220-144">Обо всем остальном позаботится среда выполнения.</span><span class="sxs-lookup"><span data-stu-id="41220-144">The runtime will take care of everything else.</span></span>

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

<span data-ttu-id="41220-145">Перед рассмотрением примера следует упомянуть сигнатуры неуправляемых функций, с которыми нам предстоит работать.</span><span class="sxs-lookup"><span data-stu-id="41220-145">Before we walk through our example, it is good to go over the signatures of the unmanaged functions we need to work with.</span></span> <span data-ttu-id="41220-146">Функция, которую требуется вызвать для перечисления всех окон, имеет следующую сигнатуру: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="41220-146">The function we want to call to enumerate all of the windows has the following signature: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span></span>

<span data-ttu-id="41220-147">Первый параметр — это обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="41220-147">The first parameter is a callback.</span></span> <span data-ttu-id="41220-148">Он имеет следующую сигнатуру: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="41220-148">The said callback has the following signature: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span></span>

<span data-ttu-id="41220-149">Учитывая это, рассмотрим пример:</span><span class="sxs-lookup"><span data-stu-id="41220-149">With this in mind, let’s walk through the example:</span></span>

*   <span data-ttu-id="41220-150">Строка 8 определяет делегат, который соответствует сигнатуре обратного вызова из неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="41220-150">Line #8 in the example defines a delegate that matches the signature of the callback from unmanaged code.</span></span> <span data-ttu-id="41220-151">Обратите внимание, как типы LPARAM и HWND представлены с помощью `IntPtr` в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="41220-151">Notice how the LPARAM and HWND types are represented using `IntPtr` in the managed code.</span></span>
*   <span data-ttu-id="41220-152">Строки 10 и 11 вводят функцию `EnumWindows` из библиотеки user32.dll.</span><span class="sxs-lookup"><span data-stu-id="41220-152">Lines #10 and #11 introduce the `EnumWindows` function from the user32.dll library.</span></span>
*   <span data-ttu-id="41220-153">Строки 13–16 реализуют делегат.</span><span class="sxs-lookup"><span data-stu-id="41220-153">Lines #13 - 16 implement the delegate.</span></span> <span data-ttu-id="41220-154">В этом простом примере мы просто выводим маркер на консоль.</span><span class="sxs-lookup"><span data-stu-id="41220-154">For this simple example, we just want to output the handle to the console.</span></span>
*   <span data-ttu-id="41220-155">Наконец, в строке 19 мы вызываем внешний метод и передаем делегат.</span><span class="sxs-lookup"><span data-stu-id="41220-155">Finally, in line #19 we invoke the external method and pass in the delegate.</span></span>

<span data-ttu-id="41220-156">Ниже приведены примеры для Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="41220-156">The Linux and macOS examples are shown below.</span></span> <span data-ttu-id="41220-157">В них мы используем функцию `ftw`, которую можно найти в библиотеке C `libc`.</span><span class="sxs-lookup"><span data-stu-id="41220-157">For them, we use the `ftw` function that can be found in `libc`, the C library.</span></span> <span data-ttu-id="41220-158">Эта функция используется для обхода иерархий каталогов и принимает указатель функции в качестве одного из своих параметров.</span><span class="sxs-lookup"><span data-stu-id="41220-158">This function is used to traverse directory hierarchies and it takes a pointer to a function as one of its parameters.</span></span> <span data-ttu-id="41220-159">Она имеет следующую сигнатуру: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span><span class="sxs-lookup"><span data-stu-id="41220-159">The said function has the following signature: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span></span>

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

<span data-ttu-id="41220-160">В примере для macOS используется та же функция. Единственное отличие состоит в аргументе для атрибута `DllImport`, так как macOS сохраняет `libc` в другом месте.</span><span class="sxs-lookup"><span data-stu-id="41220-160">macOS example uses the same function, and the only difference is the argument to the `DllImport` attribute, as macOS keeps `libc` in a different place.</span></span>

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

<span data-ttu-id="41220-161">Оба приведенных выше примера зависят от параметров, и в обоих случаях параметры задаются в виде управляемых типов.</span><span class="sxs-lookup"><span data-stu-id="41220-161">Both of the above examples depend on parameters, and in both cases, the parameters are given as managed types.</span></span> <span data-ttu-id="41220-162">На другой стороне среда выполнения преобразует их в эквивалентные.</span><span class="sxs-lookup"><span data-stu-id="41220-162">Runtime does the "right thing" and processes these into its equivalents on the other side.</span></span> <span data-ttu-id="41220-163">Поскольку этот процесс очень важен для написания качественного кода взаимодействия на уровне машинного кода, давайте рассмотрим, что происходит, когда среда выполнения производит _маршалинг_ типов.</span><span class="sxs-lookup"><span data-stu-id="41220-163">Since this process is really important to writing quality native interop code, let’s take a look at what happens when the runtime _marshals_ the types.</span></span>

## <a name="type-marshalling"></a><span data-ttu-id="41220-164">Маршалинг типов</span><span class="sxs-lookup"><span data-stu-id="41220-164">Type marshalling</span></span>

<span data-ttu-id="41220-165">**Маршалинг** — это процесс преобразования типов, когда им требуется перейти из управляемого кода в машинный и наоборот.</span><span class="sxs-lookup"><span data-stu-id="41220-165">**Marshalling** is the process of transforming types when they need to cross the managed boundary into native and vice versa.</span></span>

<span data-ttu-id="41220-166">Необходимость в маршалинге вызвана тем, что типы в управляемом и неуправляемом коде различаются.</span><span class="sxs-lookup"><span data-stu-id="41220-166">The reason marshalling is needed is because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="41220-167">Например, в управляемом коде имеется `String`, а в неуправляемом строки могут иметь различный формат: Юникод, отличный от Юникода, с конечным символом NULL, ASCII и т. д. По умолчанию подсистема P/Invoke пытается выбрать правильное решение на основе [поведения по умолчанию](../../docs/framework/interop/default-marshaling-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="41220-167">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem will try to do the right thing based on the [default behavior](../../docs/framework/interop/default-marshaling-behavior.md).</span></span> <span data-ttu-id="41220-168">Однако в ситуациях, когда требуется дополнительный контроль, можно применить атрибут [MarshalAs](xref:System.Runtime.InteropServicxes.MarshalAs), чтобы указать ожидаемый тип на стороне неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="41220-168">However, for those situations where you need extra control, you can employ the [MarshalAs](xref:System.Runtime.InteropServicxes.MarshalAs) attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="41220-169">Например, если строка должна передаваться в виде строки ANSI с конечным символом NULL, это можно сделать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="41220-169">For instance, if we want the string to be sent as a null-terminated ANSI string, we could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

### <a name="marshalling-classes-and-structs"></a><span data-ttu-id="41220-170">Маршалинг классов и структур</span><span class="sxs-lookup"><span data-stu-id="41220-170">Marshalling classes and structs</span></span>

<span data-ttu-id="41220-171">Другим аспектом маршалинга типов является способ передачи структуры в неуправляемый метод.</span><span class="sxs-lookup"><span data-stu-id="41220-171">Another aspect of type marshalling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="41220-172">Например, некоторые неуправляемые методы требуют указания структуры в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="41220-172">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="41220-173">В таких случаях требуется создать соответствующую структуру или соответствующий класс в управляемом коде для использования в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="41220-173">In these cases, we need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="41220-174">Однако простого определения класса недостаточно. Нужно также сообщить маршалеру, как сопоставлять поля класса с неуправляемой структурой.</span><span class="sxs-lookup"><span data-stu-id="41220-174">However, just defining the class is not enough, we also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="41220-175">Именно для этого и используется атрибут `StructLayout`.</span><span class="sxs-lookup"><span data-stu-id="41220-175">This is where the `StructLayout` attribute comes into play.</span></span>

```csharp
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

<span data-ttu-id="41220-176">Выше приведен простой пример вызова функции `GetSystemTime()`.</span><span class="sxs-lookup"><span data-stu-id="41220-176">The example above shows off a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="41220-177">Интерес представляет строка 4.</span><span class="sxs-lookup"><span data-stu-id="41220-177">The interesting bit is on line 4.</span></span> <span data-ttu-id="41220-178">Атрибут указывает, что поля класса должны последовательно сопоставляться со структурой на другой (неуправляемой) стороне.</span><span class="sxs-lookup"><span data-stu-id="41220-178">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="41220-179">Это означает, что имена полей не важны, важен только их порядок, так как он должен соответствовать следующей неуправляемой структуре:</span><span class="sxs-lookup"><span data-stu-id="41220-179">This means that the naming of the fields is not important, only their order is important, as it needs to correspond to the unmanaged struct, shown below:</span></span>

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

<span data-ttu-id="41220-180">Мы уже видели подобный подход для Linux и macOS в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="41220-180">We already saw the Linux and macOS example for this in the previous example.</span></span> <span data-ttu-id="41220-181">Ниже он повторяется снова.</span><span class="sxs-lookup"><span data-stu-id="41220-181">It is shown again below.</span></span>

```csharp
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

<span data-ttu-id="41220-182">Класс `StatClass` представляет структуру, возвращаемую системным вызовом `stat` в системах UNIX.</span><span class="sxs-lookup"><span data-stu-id="41220-182">The `StatClass` class represents a structure that is returned by the `stat` system call on UNIX systems.</span></span> <span data-ttu-id="41220-183">Он представляет сведения о заданном файле.</span><span class="sxs-lookup"><span data-stu-id="41220-183">It represents information about a given file.</span></span> <span data-ttu-id="41220-184">Приведенный выше класс является представлением структуры stat в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="41220-184">The class above is the stat struct representation in managed code.</span></span> <span data-ttu-id="41220-185">Еще раз отметим, что поля в классе обязательно должны находиться в том же порядке, что в собственной структуре (их можно найти, внимательно изучив страницы справки по выбранной реализации UNIX), и иметь тот же тип.</span><span class="sxs-lookup"><span data-stu-id="41220-185">Again, the fields in the class have to be in the same order as the native struct (you can find these by perusing man pages on your favorite UNIX implementation) and they have to be of the same underlying type.</span></span>

## <a name="more-resources"></a><span data-ttu-id="41220-186">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="41220-186">More resources</span></span>

*   <span data-ttu-id="41220-187">[Вики-сайт PInvoke.net](https://www.pinvoke.net/) — это отличный ресурс с информацией о распространенных API Win32 и способах их вызова.</span><span class="sxs-lookup"><span data-stu-id="41220-187">[PInvoke.net wiki](https://www.pinvoke.net/) an excellent Wiki with information on common Win32 APIs and how to call them.</span></span>
*   [<span data-ttu-id="41220-188">Сведения о P/Invoke на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="41220-188">P/Invoke on MSDN</span></span>](https://msdn.microsoft.com/library/zbz07712.aspx)
*   [<span data-ttu-id="41220-189">Документация Mono по P/Invoke</span><span class="sxs-lookup"><span data-stu-id="41220-189">Mono documentation on P/Invoke</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/)

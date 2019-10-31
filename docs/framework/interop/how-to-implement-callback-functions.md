---
title: Практическое руководство. Реализация функций обратного вызова
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- callback function, implementing
ms.assetid: e55b3712-b9ea-4453-bd9a-ad5cfa2f6bfa
ms.openlocfilehash: 23355e16127b45c26a1d950c6a8b3cc27e265781
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123886"
---
# <a name="how-to-implement-callback-functions"></a><span data-ttu-id="710b3-102">Практическое руководство. Реализация функций обратного вызова</span><span class="sxs-lookup"><span data-stu-id="710b3-102">How to: Implement Callback Functions</span></span>
<span data-ttu-id="710b3-103">В приведенных ниже процедуре и примере показано, как, используя вызов неуправляемого кода, можно напечатать из управляемого приложения значение дескриптора для каждого окна на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="710b3-103">The following procedure and example demonstrate how a managed application, using platform invoke, can print the handle value for each window on the local computer.</span></span> <span data-ttu-id="710b3-104">В частности, для печати значения дескриптора окна в процедуре и примере используется функция **EnumWindows**, которая просматривает список окон, и управляемая функция обратного вызова CallBack.</span><span class="sxs-lookup"><span data-stu-id="710b3-104">Specifically, the procedure and example use the **EnumWindows** function to step through the list of windows and a managed callback function (named CallBack) to print the value of the window handle.</span></span>  
  
### <a name="to-implement-a-callback-function"></a><span data-ttu-id="710b3-105">Реализация функции обратного вызова</span><span class="sxs-lookup"><span data-stu-id="710b3-105">To implement a callback function</span></span>  
  
1. <span data-ttu-id="710b3-106">Прежде чем приступить к реализации, обратите внимание на сигнатуру функции **EnumWindows**.</span><span class="sxs-lookup"><span data-stu-id="710b3-106">Look at the signature for the **EnumWindows** function before going further with the implementation.</span></span> <span data-ttu-id="710b3-107">Функция **EnumWindows** имеет следующую сигнатуру:</span><span class="sxs-lookup"><span data-stu-id="710b3-107">**EnumWindows** has the following signature:</span></span>  
  
    ```cpp
    BOOL EnumWindows(WNDENUMPROC lpEnumFunc, LPARAM lParam)
    ```
  
     <span data-ttu-id="710b3-108">Признаком необходимости обратного вызова для функции является наличие аргумента **lpEnumFunc**.</span><span class="sxs-lookup"><span data-stu-id="710b3-108">One clue that this function requires a callback is the presence of the **lpEnumFunc** argument.</span></span> <span data-ttu-id="710b3-109">Обычно в именах аргументов, которые принимают указатель на функцию обратного вызова, присутствует префикс **lp** (long pointer, длинный указатель) и суффикс **Func**.</span><span class="sxs-lookup"><span data-stu-id="710b3-109">It is common to see the **lp** (long pointer) prefix combined with the **Func** suffix in the name of arguments that take a pointer to a callback function.</span></span> <span data-ttu-id="710b3-110">Документацию по функциям Win32 см. в Microsoft Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="710b3-110">For documentation about Win32 functions, see the Microsoft Platform SDK.</span></span>  
  
2. <span data-ttu-id="710b3-111">Создайте управляемую функцию обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="710b3-111">Create the managed callback function.</span></span> <span data-ttu-id="710b3-112">В примере объявляется тип делегата `CallBack`, который принимает два аргумента (**hwnd** и **lparam**).</span><span class="sxs-lookup"><span data-stu-id="710b3-112">The example declares a delegate type, called `CallBack`, which takes two arguments (**hwnd** and **lparam**).</span></span> <span data-ttu-id="710b3-113">Первый аргумент — это дескриптор окна, а второй определяется приложением.</span><span class="sxs-lookup"><span data-stu-id="710b3-113">The first argument is a handle to the window; the second argument is application-defined.</span></span> <span data-ttu-id="710b3-114">В этом выпуске оба аргумента должны быть целыми числами.</span><span class="sxs-lookup"><span data-stu-id="710b3-114">In this release, both arguments must be integers.</span></span>  
  
     <span data-ttu-id="710b3-115">Функции обратного вызова обычно возвращают ненулевые значения, сообщая об успешном выполнении, и ноль, сообщая о сбое.</span><span class="sxs-lookup"><span data-stu-id="710b3-115">Callback functions generally return nonzero values to indicate success and zero to indicate failure.</span></span> <span data-ttu-id="710b3-116">В этом примере для продолжения перечисления в явном виде устанавливается возвращаемое значение **true**.</span><span class="sxs-lookup"><span data-stu-id="710b3-116">This example explicitly sets the return value to **true** to continue the enumeration.</span></span>  
  
3. <span data-ttu-id="710b3-117">Создайте делегат и передайте его в качестве аргумента в функцию **EnumWindows**.</span><span class="sxs-lookup"><span data-stu-id="710b3-117">Create a delegate and pass it as an argument to the **EnumWindows** function.</span></span> <span data-ttu-id="710b3-118">Вызов неуправляемого кода автоматически преобразует делегат в знакомый формат обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="710b3-118">Platform invoke converts the delegate to a familiar callback format automatically.</span></span>  
  
4. <span data-ttu-id="710b3-119">Убедитесь в том, что сборщик мусора не освобождает делегат до завершения выполнения функции обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="710b3-119">Ensure that the garbage collector does not reclaim the delegate before the callback function completes its work.</span></span> <span data-ttu-id="710b3-120">При передаче делегата в качестве параметра или поля структуры он не уничтожается в течение всего вызова.</span><span class="sxs-lookup"><span data-stu-id="710b3-120">When you pass a delegate as a parameter, or pass a delegate contained as a field in a structure, it remains uncollected for the duration of the call.</span></span> <span data-ttu-id="710b3-121">Таким образом, как показано в примере перечисления ниже, функция обратного вызова завершает работу, прежде чем вызов возвращает управление, не требуя никаких дополнительных действий со стороны управляемого вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="710b3-121">So, as is the case in the following enumeration example, the callback function completes its work before the call returns and requires no additional action by the managed caller.</span></span>  
  
     <span data-ttu-id="710b3-122">Но если функция обратного вызова может быть вызвана после возвращения вызова, управляемый вызывающий объект должен выполнить действия, гарантирующие, что делегат не будет уничтожен, пока функция обратного вызова не завершит работу.</span><span class="sxs-lookup"><span data-stu-id="710b3-122">If, however, the callback function can be invoked after the call returns, the managed caller must take steps to ensure that the delegate remains uncollected until the callback function finishes.</span></span> <span data-ttu-id="710b3-123">Подробную информацию о предотвращении сборки мусора см. в разделе [Маршалинг взаимодействия](interop-marshaling.md) в подразделе, посвященном вызову неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="710b3-123">For detailed information about preventing garbage collection, see [Interop Marshaling](interop-marshaling.md) with Platform Invoke.</span></span>  
  
## <a name="example"></a><span data-ttu-id="710b3-124">Пример</span><span class="sxs-lookup"><span data-stu-id="710b3-124">Example</span></span>  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
  
Public Delegate Function CallBack( _  
hwnd As Integer, lParam As Integer) As Boolean  
  
Public Class EnumReportApp  
  
    Declare Function EnumWindows Lib "user32" ( _  
       x As CallBack, y As Integer) As Integer  
  
    Public Shared Sub Main()  
        EnumWindows(AddressOf EnumReportApp.Report, 0)  
    End Sub 'Main  
  
    Public Shared Function Report(hwnd As Integer, lParam As Integer) _  
    As Boolean  
        Console.Write("Window handle is ")  
        Console.WriteLine(hwnd)  
        Return True  
    End Function 'Report  
End Class 'EnumReportApp  
```  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public delegate bool CallBack(int hwnd, int lParam);  
  
public class EnumReportApp  
{  
    [DllImport("user32")]  
    public static extern int EnumWindows(CallBack x, int y);   
  
    public static void Main()   
    {  
        CallBack myCallBack = new CallBack(EnumReportApp.Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    public static bool Report(int hwnd, int lParam)  
    {   
        Console.Write("Window handle is ");  
        Console.WriteLine(hwnd);  
        return true;  
    }  
}  
```  
  
```cpp  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// A delegate type.  
delegate bool CallBack(int hwnd, int lParam);  
  
// Managed type with the method to call.  
ref class EnumReport  
{  
// Report the window handle.  
public:  
    [DllImport("user32")]  
    static int EnumWindows(CallBack^ x, int y);  
  
    static void Main()  
    {  
        EnumReport^ er = gcnew EnumReport;  
        CallBack^ myCallBack = gcnew CallBack(&EnumReport::Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    static bool Report(int hwnd, int lParam)  
    {  
       Console::Write(L"Window handle is ");  
       Console::WriteLine(hwnd);  
       return true;  
    }  
};  
  
int main()  
{  
    EnumReport::Main();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="710b3-125">См. также</span><span class="sxs-lookup"><span data-stu-id="710b3-125">See also</span></span>

- [<span data-ttu-id="710b3-126">Функции обратного вызова</span><span class="sxs-lookup"><span data-stu-id="710b3-126">Callback Functions</span></span>](callback-functions.md)
- [<span data-ttu-id="710b3-127">Вызов функции DLL</span><span class="sxs-lookup"><span data-stu-id="710b3-127">Calling a DLL Function</span></span>](calling-a-dll-function.md)

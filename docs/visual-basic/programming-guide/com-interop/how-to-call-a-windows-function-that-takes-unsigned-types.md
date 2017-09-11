---
title: "Практическое руководство: вызов функции Windows, принимающей значение беззнакового типа (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Windows functions, calling
- unsigned data types
- UShort data type, using
- functions [Visual Basic], calling Windows functions
- ULong data type, using
- UInteger data type, using
- data types [Visual Basic], using
- unsigned types
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types, using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7b6b1d46b6ccab0ec8d63fb8b7d8722b518b81b4
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="a5c8d-102">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5c8d-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>
<span data-ttu-id="a5c8d-103">При использовании класса, модуля или структуры, имеющих члены беззнаковых целых типов, доступ к этим членам с помощью [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5c8d-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="a5c8d-104">Для вызова функции Windows, которая принимает тип без знака</span><span class="sxs-lookup"><span data-stu-id="a5c8d-104">To call a Windows function that takes an unsigned type</span></span>  
  
1.  <span data-ttu-id="a5c8d-105">Используйте [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) сообщить [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] библиотеку, в которой содержится функция его имя, что последовательность вызова и как преобразовать строки при его вызове.</span><span class="sxs-lookup"><span data-stu-id="a5c8d-105">Use a [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) to tell [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>  
  
2.  <span data-ttu-id="a5c8d-106">В `Declare` инструкции, используйте `UInteger`, `ULong`, `UShort`, или `Byte` соответствующим образом для каждого параметра с типом без знака.</span><span class="sxs-lookup"><span data-stu-id="a5c8d-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>  
  
3.  <span data-ttu-id="a5c8d-107">Обратитесь к документации Windows функции, вызываемой для поиска имен и значений констант, которые он использует.</span><span class="sxs-lookup"><span data-stu-id="a5c8d-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="a5c8d-108">Многие из них определены в файле WinUser.h.</span><span class="sxs-lookup"><span data-stu-id="a5c8d-108">Many of these are defined in the WinUser.h file.</span></span>  
  
4.  <span data-ttu-id="a5c8d-109">Объявите необходимые константы в коде.</span><span class="sxs-lookup"><span data-stu-id="a5c8d-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="a5c8d-110">Многие константы Windows-32-разрядные беззнаковые значения, их следует объявлять эти `As``UInteger`.</span><span class="sxs-lookup"><span data-stu-id="a5c8d-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As``UInteger`.</span></span>  
  
5.  <span data-ttu-id="a5c8d-111">Вызовите функцию обычным образом.</span><span class="sxs-lookup"><span data-stu-id="a5c8d-111">Call the function in the normal way.</span></span> <span data-ttu-id="a5c8d-112">В следующем примере вызывается функция Windows `MessageBox`, который принимает в качестве аргумента целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="a5c8d-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>  
  
    ```  
    Public Class windowsMessage  
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (  
            ByVal hWnd As Integer,   
            ByVal lpText As String,   
            ByVal lpCaption As String,   
            ByVal uType As UInteger) As Integer  
        Private Const MB_OK As UInteger = 0  
        Private Const MB_ICONEXCLAMATION As UInteger = &H30  
        Private Const IDOK As UInteger = 1  
        Private Const IDCLOSE As UInteger = 8  
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION  
        Public Function messageThroughWindows() As String  
            Dim r As Integer = mb(0, "Click OK if you see this!",   
                "Windows API call", c)  
            Dim s As String = "Windows API MessageBox returned " &  
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &  
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"  
            Return s  
        End Function  
    End Class  
    ```  
  
     <span data-ttu-id="a5c8d-113">Можно проверить функцию `messageThroughWindows` следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="a5c8d-113">You can test the function `messageThroughWindows` with the following code.</span></span>  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="a5c8d-114">`UInteger`, `ULong`, `UShort`, И `SByte` типы данных не являются частью [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), поэтому в CLS-совместимом коде нельзя использовать компонент, который использует их.</span><span class="sxs-lookup"><span data-stu-id="a5c8d-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a5c8d-115">Вызов неуправляемого кода, такие как интерфейс (API) Windows подвергает ваш код потенциальной опасности.</span><span class="sxs-lookup"><span data-stu-id="a5c8d-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a5c8d-116">Вызов Windows API требует разрешение неуправляемого кода, что может повлиять на его выполнение в случаях частичного доверия.</span><span class="sxs-lookup"><span data-stu-id="a5c8d-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="a5c8d-117">Дополнительные сведения см. в разделе <xref:System.Security.Permissions.SecurityPermission>и [разрешений доступа к коду](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</xref:System.Security.Permissions.SecurityPermission></span><span class="sxs-lookup"><span data-stu-id="a5c8d-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5c8d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a5c8d-118">See Also</span></span>  
 <span data-ttu-id="a5c8d-119">[Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="a5c8d-119">[Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="a5c8d-120"> [Целочисленный тип данных](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="a5c8d-120"> [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span></span>  
<span data-ttu-id="a5c8d-121"> [Тип данных UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="a5c8d-121"> [UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) </span></span>  
<span data-ttu-id="a5c8d-122"> [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a5c8d-122"> [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="a5c8d-123"> [Пошаговое руководство. Вызов API-интерфейсов Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)</span><span class="sxs-lookup"><span data-stu-id="a5c8d-123"> [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)</span></span>

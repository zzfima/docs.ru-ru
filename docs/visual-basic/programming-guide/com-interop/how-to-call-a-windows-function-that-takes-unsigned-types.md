---
title: Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
ms.openlocfilehash: d66b74f06abe6b337c24859c444f7a8c2aa52c13
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421527"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="2558c-102">Практическое руководство. Вызов функции Windows, принимающей значение беззнакового типа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2558c-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>
<span data-ttu-id="2558c-103">При использовании класса, модуля или структура, которая содержит члены типов целое число без знака, можно получить доступ к этим членам с помощью Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2558c-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with Visual Basic.</span></span>  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="2558c-104">Для вызова функции Windows, принимающей тип без знака</span><span class="sxs-lookup"><span data-stu-id="2558c-104">To call a Windows function that takes an unsigned type</span></span>  
  
1.  <span data-ttu-id="2558c-105">Используйте [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) сообщить Visual Basic, какая из библиотек содержит функцию его имя, что последовательность вызова и как преобразовать строки, при его вызове.</span><span class="sxs-lookup"><span data-stu-id="2558c-105">Use a [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) to tell Visual Basic which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>  
  
2.  <span data-ttu-id="2558c-106">В `Declare` выражение use `UInteger`, `ULong`, `UShort`, или `Byte` соответствующим образом для каждого параметра с типом без знака.</span><span class="sxs-lookup"><span data-stu-id="2558c-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>  
  
3.  <span data-ttu-id="2558c-107">См. в документации для функции Windows, чтобы найти имена и значения констант, используемых при вызове.</span><span class="sxs-lookup"><span data-stu-id="2558c-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="2558c-108">Многие из них определяются в файле WinUser.h.</span><span class="sxs-lookup"><span data-stu-id="2558c-108">Many of these are defined in the WinUser.h file.</span></span>  
  
4.  <span data-ttu-id="2558c-109">Объявите необходимые константы в коде.</span><span class="sxs-lookup"><span data-stu-id="2558c-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="2558c-110">Многие константы Windows-32-разрядных неподписанных значений, их следует объявлять `As``UInteger`.</span><span class="sxs-lookup"><span data-stu-id="2558c-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As``UInteger`.</span></span>  
  
5.  <span data-ttu-id="2558c-111">Вызовите функцию обычным способом.</span><span class="sxs-lookup"><span data-stu-id="2558c-111">Call the function in the normal way.</span></span> <span data-ttu-id="2558c-112">В следующем примере вызывается функция Windows `MessageBox`, который принимает в качестве аргумента целого числа без знака.</span><span class="sxs-lookup"><span data-stu-id="2558c-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>  
  
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
  
     <span data-ttu-id="2558c-113">Можно протестировать функцию `messageThroughWindows` следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="2558c-113">You can test the function `messageThroughWindows` with the following code.</span></span>  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="2558c-114">`UInteger`, `ULong`, `UShort`, И `SByte` типы данных не являются частью [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), поэтому CLS-совместимого кода нельзя использовать компонент, который они используются.</span><span class="sxs-lookup"><span data-stu-id="2558c-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="2558c-115">Вызов неуправляемого кода, таких как интерфейс (API), Windows предоставляет код, чтобы потенциальные угрозы безопасности.</span><span class="sxs-lookup"><span data-stu-id="2558c-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="2558c-116">Вызов Windows API требует разрешение неуправляемого кода, которое может повлиять на выполнение в ситуациях частичного доверия.</span><span class="sxs-lookup"><span data-stu-id="2558c-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="2558c-117">Дополнительные сведения см. в разделе <xref:System.Security.Permissions.SecurityPermission> и [разрешений доступа к коду](https://msdn.microsoft.com/library/e5ae402f-6dda-4732-bbe8-77296630f675).</span><span class="sxs-lookup"><span data-stu-id="2558c-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](https://msdn.microsoft.com/library/e5ae402f-6dda-4732-bbe8-77296630f675).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2558c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2558c-118">See Also</span></span>  
 [<span data-ttu-id="2558c-119">Типы данных</span><span class="sxs-lookup"><span data-stu-id="2558c-119">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="2558c-120">Тип данных Integer</span><span class="sxs-lookup"><span data-stu-id="2558c-120">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="2558c-121">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="2558c-121">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
 [<span data-ttu-id="2558c-122">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="2558c-122">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="2558c-123">Пошаговое руководство. Вызов API-интерфейсов Windows</span><span class="sxs-lookup"><span data-stu-id="2558c-123">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)

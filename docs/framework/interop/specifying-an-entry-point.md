---
title: Задание точки входа
ms.date: 03/30/2017
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
ms.openlocfilehash: c5f8f735dd3e8c359f88044a532c29303237acc8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181315"
---
# <a name="specifying-an-entry-point"></a><span data-ttu-id="20e6e-102">Задание точки входа</span><span class="sxs-lookup"><span data-stu-id="20e6e-102">Specifying an Entry Point</span></span>

<span data-ttu-id="20e6e-103">Точка входа определяет расположение функции в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="20e6e-103">An entry point identifies the location of a function in a DLL.</span></span> <span data-ttu-id="20e6e-104">В управляемом проекте исходное имя или порядковый номер точки входа целевой функции определяет эту функцию в границах взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="20e6e-104">Within a managed project, the original name or ordinal entry point of a target function identifies that function across the interoperation boundary.</span></span> <span data-ttu-id="20e6e-105">Вы можете сопоставить точку входа с другим именем, чтобы фактически переименовать функцию.</span><span class="sxs-lookup"><span data-stu-id="20e6e-105">Further, you can map the entry point to a different name, effectively renaming the function.</span></span>  
  
 <span data-ttu-id="20e6e-106">Ниже приводится список возможных причин переименования функции DLL:</span><span class="sxs-lookup"><span data-stu-id="20e6e-106">The following is a list of possible reasons to rename a DLL function:</span></span>  
  
- <span data-ttu-id="20e6e-107">чтобы избежать использования имен функций API, в которых учитывается регистр символов;</span><span class="sxs-lookup"><span data-stu-id="20e6e-107">To avoid using case-sensitive API function names</span></span>  
  
- <span data-ttu-id="20e6e-108">чтобы привести имена в соответствие с существующими стандартами именования;</span><span class="sxs-lookup"><span data-stu-id="20e6e-108">To comply with existing naming standards</span></span>  
  
- <span data-ttu-id="20e6e-109">чтобы сделать возможным вызов функций, принимающих данные разных типов (путем объявления нескольких версий одной и той же функции DLL);</span><span class="sxs-lookup"><span data-stu-id="20e6e-109">To accommodate functions that take different data types (by declaring multiple versions of the same DLL function)</span></span>  
  
- <span data-ttu-id="20e6e-110">чтобы упростить применение интерфейсов API, которые содержат версии функции для ANSI и Юникода.</span><span class="sxs-lookup"><span data-stu-id="20e6e-110">To simplify using APIs that contain ANSI and Unicode versions</span></span>  
  
 <span data-ttu-id="20e6e-111">В этом разделе показано, как переименовать функцию DLL в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="20e6e-111">This topic demonstrates how to rename a DLL function in managed code.</span></span>  
  
## <a name="renaming-a-function-in-visual-basic"></a><span data-ttu-id="20e6e-112">Переименование функции в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20e6e-112">Renaming a Function in Visual Basic</span></span>  

<span data-ttu-id="20e6e-113">В Visual Basic для установки поля <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> используется ключевое слово **Function** в операторе **Declare**.</span><span class="sxs-lookup"><span data-stu-id="20e6e-113">Visual Basic uses the **Function** keyword in the **Declare** statement to set the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field.</span></span> <span data-ttu-id="20e6e-114">В приведенном ниже примере показан базовый вариант объявления.</span><span class="sxs-lookup"><span data-stu-id="20e6e-114">The following example shows a basic declaration.</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
<span data-ttu-id="20e6e-115">Как показано в следующем примере, можно заменить точку входа **MessageBox** на **MsgBox**, включив в определение ключевое слово **Alias**.</span><span class="sxs-lookup"><span data-stu-id="20e6e-115">You can replace the **MessageBox** entry point with **MsgBox** by including the **Alias** keyword in your definition, as shown in the following example.</span></span> <span data-ttu-id="20e6e-116">В обоих примерах ключевое слово **Auto** позволяет не указывать версию кодировки для точки входа.</span><span class="sxs-lookup"><span data-stu-id="20e6e-116">In both examples the **Auto** keyword eliminates the need to specify the character-set version of the entry point.</span></span> <span data-ttu-id="20e6e-117">Дополнительные сведения о выборе кодировки см. в разделе [Определение кодировки](specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="20e6e-117">For more information about selecting a character set, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MsgBox _
        Lib "user32.dll" Alias "MessageBox" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="renaming-a-function-in-c-and-c"></a><span data-ttu-id="20e6e-118">Переименование функции в C# и C++</span><span class="sxs-lookup"><span data-stu-id="20e6e-118">Renaming a Function in C# and C++</span></span>  
 <span data-ttu-id="20e6e-119">Для задания функции DLL по имени или порядковому номеру можно использовать поле <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="20e6e-119">You can use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field to specify a DLL function by name or ordinal.</span></span> <span data-ttu-id="20e6e-120">Если имя функции в определении метода совпадает с именем точки входа в библиотеке DLL, явно задавать функцию с помощью поля **EntryPoint** не требуется.</span><span class="sxs-lookup"><span data-stu-id="20e6e-120">If the name of the function in your method definition is the same as the entry point in the DLL, you do not have to explicitly identify the function with the **EntryPoint** field.</span></span> <span data-ttu-id="20e6e-121">В противном случае, чтобы указать имя или порядковый номер, следует использовать одну из следующих форм атрибута:</span><span class="sxs-lookup"><span data-stu-id="20e6e-121">Otherwise, use one of the following attribute forms to indicate a name or ordinal:</span></span>  
  
```csharp
[DllImport("DllName", EntryPoint = "Functionname")]
[DllImport("DllName", EntryPoint = "#123")]
```
  
 <span data-ttu-id="20e6e-122">Обратите внимание, что порядковому номеру должен предшествовать знак #.</span><span class="sxs-lookup"><span data-stu-id="20e6e-122">Notice that you must prefix an ordinal with the pound sign (#).</span></span>  
  
 <span data-ttu-id="20e6e-123">В приведенном ниже примере показан способ замены в коде **MessageBoxA** на **MsgBox** с помощью поля **EntryPoint**.</span><span class="sxs-lookup"><span data-stu-id="20e6e-123">The following example demonstrates how to replace **MessageBoxA** with **MsgBox** in your code by using the **EntryPoint** field.</span></span>  
  
```csharp
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll", EntryPoint = "MessageBoxA")]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```
  
```cpp
using namespace System;
using namespace System::Runtime::InteropServices;

typedef void* HWND;
[DllImport("user32", EntryPoint = "MessageBoxA")]
extern "C" int MsgBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a><span data-ttu-id="20e6e-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="20e6e-124">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="20e6e-125">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="20e6e-125">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="20e6e-126">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="20e6e-126">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="20e6e-127">Маршалинг данных при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="20e6e-127">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)

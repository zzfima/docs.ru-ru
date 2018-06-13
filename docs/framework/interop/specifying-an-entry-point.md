---
title: Задание точки входа
ms.date: 03/30/2017
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31bb28b5bda51fb1579021e47b8d5ec49adb644e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33388837"
---
# <a name="specifying-an-entry-point"></a><span data-ttu-id="c99e1-102">Задание точки входа</span><span class="sxs-lookup"><span data-stu-id="c99e1-102">Specifying an Entry Point</span></span>
<span data-ttu-id="c99e1-103">Точка входа определяет расположение функции в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="c99e1-103">An entry point identifies the location of a function in a DLL.</span></span> <span data-ttu-id="c99e1-104">В управляемом проекте исходное имя или порядковый номер точки входа целевой функции определяет эту функцию в границах взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="c99e1-104">Within a managed project, the original name or ordinal entry point of a target function identifies that function across the interoperation boundary.</span></span> <span data-ttu-id="c99e1-105">Вы можете сопоставить точку входа с другим именем, чтобы фактически переименовать функцию.</span><span class="sxs-lookup"><span data-stu-id="c99e1-105">Further, you can map the entry point to a different name, effectively renaming the function.</span></span>  
  
 <span data-ttu-id="c99e1-106">Ниже перечислено, зачем может потребоваться переименовывать функции DLL:</span><span class="sxs-lookup"><span data-stu-id="c99e1-106">Following is a list of possible reasons to rename a DLL function:</span></span>  
  
-   <span data-ttu-id="c99e1-107">чтобы избежать использования имен функций API, в которых учитывается регистр символов;</span><span class="sxs-lookup"><span data-stu-id="c99e1-107">To avoid using case-sensitive API function names</span></span>  
  
-   <span data-ttu-id="c99e1-108">чтобы привести имена в соответствие с существующими стандартами именования;</span><span class="sxs-lookup"><span data-stu-id="c99e1-108">To comply with existing naming standards</span></span>  
  
-   <span data-ttu-id="c99e1-109">чтобы сделать возможным вызов функций, принимающих данные разных типов (путем объявления нескольких версий одной и той же функции DLL);</span><span class="sxs-lookup"><span data-stu-id="c99e1-109">To accommodate functions that take different data types (by declaring multiple versions of the same DLL function)</span></span>  
  
-   <span data-ttu-id="c99e1-110">чтобы упростить применение интерфейсов API, которые содержат версии функции для ANSI и Юникода.</span><span class="sxs-lookup"><span data-stu-id="c99e1-110">To simplify using APIs that contain ANSI and Unicode versions</span></span>  
  
 <span data-ttu-id="c99e1-111">В этом разделе показано, как переименовать функцию DLL в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="c99e1-111">This topic demonstrates how to rename a DLL function in managed code.</span></span>  
  
## <a name="renaming-a-function-in-visual-basic"></a><span data-ttu-id="c99e1-112">Переименование функции в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c99e1-112">Renaming a Function in Visual Basic</span></span>  
 <span data-ttu-id="c99e1-113">В Visual Basic для установки поля <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> используется ключевое слово **Function** в операторе **Declare**.</span><span class="sxs-lookup"><span data-stu-id="c99e1-113">Visual Basic uses the **Function** keyword in the **Declare** statement to set the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field.</span></span> <span data-ttu-id="c99e1-114">В приведенном ниже примере показан базовый вариант объявления.</span><span class="sxs-lookup"><span data-stu-id="c99e1-114">The following example shows a basic declaration.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
 <span data-ttu-id="c99e1-115">Как показано в следующем примере, можно заменить точку входа **MessageBox** на **MsgBox**, включив в определение ключевое слово **Alias**.</span><span class="sxs-lookup"><span data-stu-id="c99e1-115">You can replace the **MessageBox** entry point with **MsgBox** by including the **Alias** keyword in your definition, as shown in the following example.</span></span> <span data-ttu-id="c99e1-116">В обоих примерах ключевое слово **Auto** позволяет не указывать версию кодировки для точки входа.</span><span class="sxs-lookup"><span data-stu-id="c99e1-116">In both examples the **Auto** keyword eliminates the need to specify the character-set version of the entry point.</span></span> <span data-ttu-id="c99e1-117">Дополнительные сведения о выборе кодировки см. в разделе [Определение кодировки](../../../docs/framework/interop/specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="c99e1-117">For more information about selecting a character set, see [Specifying a Character Set](../../../docs/framework/interop/specifying-a-character-set.md).</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MsgBox Lib "user32.dll" _  
       Alias "MessageBox" (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="renaming-a-function-in-c-and-c"></a><span data-ttu-id="c99e1-118">Переименование функции в C# и C++</span><span class="sxs-lookup"><span data-stu-id="c99e1-118">Renaming a Function in C# and C++</span></span>  
 <span data-ttu-id="c99e1-119">Для задания функции DLL по имени или порядковому номеру можно использовать поле <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c99e1-119">You can use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field to specify a DLL function by name or ordinal.</span></span> <span data-ttu-id="c99e1-120">Если имя функции в определении метода совпадает с именем точки входа в библиотеке DLL, явно задавать функцию с помощью поля **EntryPoint** не требуется.</span><span class="sxs-lookup"><span data-stu-id="c99e1-120">If the name of the function in your method definition is the same as the entry point in the DLL, you do not have to explicitly identify the function with the **EntryPoint** field.</span></span> <span data-ttu-id="c99e1-121">В противном случае, чтобы указать имя или порядковый номер, следует использовать одну из следующих форм атрибута:</span><span class="sxs-lookup"><span data-stu-id="c99e1-121">Otherwise, use one of the following attribute forms to indicate a name or ordinal:</span></span>  
  
```  
[DllImport("dllname", EntryPoint="Functionname")]  
[DllImport("dllname", EntryPoint="#123")]  
```  
  
 <span data-ttu-id="c99e1-122">Обратите внимание, что порядковому номеру должен предшествовать знак #.</span><span class="sxs-lookup"><span data-stu-id="c99e1-122">Notice that you must prefix an ordinal with the pound sign (#).</span></span>  
  
 <span data-ttu-id="c99e1-123">В приведенном ниже примере показан способ замены в коде **MessageBoxA** на **MsgBox** с помощью поля **EntryPoint**.</span><span class="sxs-lookup"><span data-stu-id="c99e1-123">The following example demonstrates how to replace **MessageBoxA** with **MsgBox** in your code by using the **EntryPoint** field.</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
  
public class Win32 {  
    [DllImport("user32.dll", EntryPoint="MessageBoxA")]  
    public static extern int MsgBox(int hWnd, String text, String caption,  
                                    uint type);  
}  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
  
typedef void* HWND;  
[DllImport("user32", EntryPoint="MessageBoxA")]  
extern "C" int MsgBox(HWND hWnd,  
                      String*  pText,  
                      String*  pCaption,  
                      unsigned int uType);  
```  
  
## <a name="see-also"></a><span data-ttu-id="c99e1-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c99e1-124">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [<span data-ttu-id="c99e1-125">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="c99e1-125">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="c99e1-126">Примеры вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="c99e1-126">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="c99e1-127">Маршалинг данных при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="c99e1-127">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)

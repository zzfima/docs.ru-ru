---
title: Пример MsgBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
ms.openlocfilehash: 9f1e6d58742f60b6043a4be9218b80b323cd523e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124113"
---
# <a name="msgbox-sample"></a><span data-ttu-id="51a22-102">Пример MsgBox</span><span class="sxs-lookup"><span data-stu-id="51a22-102">MsgBox Sample</span></span>
<span data-ttu-id="51a22-103">В этом примере демонстрируется, как передавать строковые типы по значению в качестве параметров ввода и когда следует использовать поля <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> и <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>.</span><span class="sxs-lookup"><span data-stu-id="51a22-103">This sample demonstrates how to pass string types by value as In parameters and when to use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>, and <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> fields.</span></span>  
  
 <span data-ttu-id="51a22-104">В примере используются следующие неуправляемые функции, показанные с исходными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="51a22-104">The MsgBox sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
- <span data-ttu-id="51a22-105">**MessageBox** экспортируется из User32.dll.</span><span class="sxs-lookup"><span data-stu-id="51a22-105">**MessageBox** exported from User32.dll.</span></span>  
  
    ```cpp
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 <span data-ttu-id="51a22-106">В этом примере класс `NativeMethods` содержит управляемый прототип для каждой неуправляемой функции, вызываемой классом `MsgBoxSample`.</span><span class="sxs-lookup"><span data-stu-id="51a22-106">In this sample, the `NativeMethods` class contains a managed prototype for each unmanaged function called by the `MsgBoxSample` class.</span></span> <span data-ttu-id="51a22-107">Управляемые прототипы методов `MsgBox`, `MsgBox2` и `MsgBox3` содержат разные объявления для одной и той же неуправляемой функции.</span><span class="sxs-lookup"><span data-stu-id="51a22-107">The managed prototype methods `MsgBox`, `MsgBox2`, and `MsgBox3` have different declarations for the same unmanaged function.</span></span>  
  
 <span data-ttu-id="51a22-108">Объявление `MsgBox2` приводит к выводу некорректных данных в окне сообщения, поскольку символьный тип, указанный как ANSI, не соответствует точке входа `MessageBoxW`, которая определяет функцию Юникода.</span><span class="sxs-lookup"><span data-stu-id="51a22-108">The declaration for `MsgBox2` produces incorrect output in the message box because the character type, specified as ANSI, is mismatched with the entry point `MessageBoxW`, which is the name of the Unicode function.</span></span> <span data-ttu-id="51a22-109">Объявление `MsgBox3` приводит к несоответствию между полями **EntryPoint**, **CharSet** и **ExactSpelling**.</span><span class="sxs-lookup"><span data-stu-id="51a22-109">The declaration for `MsgBox3` creates a mismatch between the **EntryPoint**, **CharSet**, and **ExactSpelling** fields.</span></span> <span data-ttu-id="51a22-110">При вызове `MsgBox3` возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="51a22-110">When called, `MsgBox3` throws an exception.</span></span> <span data-ttu-id="51a22-111">Дополнительные сведения об именовании строк и маршалинге имен см. в разделе [Определение кодировки](specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="51a22-111">For detailed information on string naming and name marshaling, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="51a22-112">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="51a22-112">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a><span data-ttu-id="51a22-113">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="51a22-113">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="51a22-114">См. также</span><span class="sxs-lookup"><span data-stu-id="51a22-114">See also</span></span>

- [<span data-ttu-id="51a22-115">Mаршалинг строк</span><span class="sxs-lookup"><span data-stu-id="51a22-115">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="51a22-116">Маршалинг по умолчанию для строк</span><span class="sxs-lookup"><span data-stu-id="51a22-116">Default Marshaling for Strings</span></span>](default-marshaling-for-strings.md)
- [<span data-ttu-id="51a22-117">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="51a22-117">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="51a22-118">Определение кодировки</span><span class="sxs-lookup"><span data-stu-id="51a22-118">Specifying a Character Set</span></span>](specifying-a-character-set.md)

---
title: "Пример MsgBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0d9be3d490a687541a0b1c7af3d90c52523413a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="msgbox-sample"></a><span data-ttu-id="08b72-102">Пример MsgBox</span><span class="sxs-lookup"><span data-stu-id="08b72-102">MsgBox Sample</span></span>
<span data-ttu-id="08b72-103">В этом примере демонстрируется, как передавать строковые типы по значению в качестве параметров ввода и когда следует использовать поля <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> и <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>.</span><span class="sxs-lookup"><span data-stu-id="08b72-103">This sample demonstrates how to pass string types by value as In parameters and when to use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>, and <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> fields.</span></span>  
  
 <span data-ttu-id="08b72-104">В примере используются следующие неуправляемые функции, показанные с исходными объявлениями:</span><span class="sxs-lookup"><span data-stu-id="08b72-104">The MsgBox sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="08b72-105">**MessageBox** экспортируется из User32.dll.</span><span class="sxs-lookup"><span data-stu-id="08b72-105">**MessageBox** exported from User32.dll.</span></span>  
  
    ```  
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 <span data-ttu-id="08b72-106">В этом примере класс `LibWrap` содержит управляемый прототип для каждой неуправляемой функции, вызываемой классом `MsgBoxSample`.</span><span class="sxs-lookup"><span data-stu-id="08b72-106">In this sample, the `LibWrap` class contains a managed prototype for each unmanaged function called by the `MsgBoxSample` class.</span></span> <span data-ttu-id="08b72-107">Управляемые прототипы методов `MsgBox`, `MsgBox2` и `MsgBox3` содержат разные объявления для одной и той же неуправляемой функции.</span><span class="sxs-lookup"><span data-stu-id="08b72-107">The managed prototype methods `MsgBox`, `MsgBox2`, and `MsgBox3` have different declarations for the same unmanaged function.</span></span>  
  
 <span data-ttu-id="08b72-108">Объявление `MsgBox2` приводит к выводу некорректных данных в окне сообщения, поскольку символьный тип, указанный как ANSI, не соответствует точке входа `MessageBoxW`, которая определяет функцию Юникода.</span><span class="sxs-lookup"><span data-stu-id="08b72-108">The declaration for `MsgBox2` produces incorrect output in the message box because the character type, specified as ANSI, is mismatched with the entry point `MessageBoxW`, which is the name of the Unicode function.</span></span> <span data-ttu-id="08b72-109">Объявление `MsgBox3` приводит к несоответствию между полями **EntryPoint**, **CharSet** и **ExactSpelling**.</span><span class="sxs-lookup"><span data-stu-id="08b72-109">The declaration for `MsgBox3` creates a mismatch between the **EntryPoint**, **CharSet**, and **ExactSpelling** fields.</span></span> <span data-ttu-id="08b72-110">При вызове `MsgBox3` возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="08b72-110">When called, `MsgBox3` throws an exception.</span></span> <span data-ttu-id="08b72-111">Дополнительные сведения об именовании строк и маршалинге имен см. в разделе [Определение кодировки](../../../docs/framework/interop/specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="08b72-111">For detailed information on string naming and name marshaling, see [Specifying a Character Set](../../../docs/framework/interop/specifying-a-character-set.md).</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="08b72-112">Объявление прототипов</span><span class="sxs-lookup"><span data-stu-id="08b72-112">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a><span data-ttu-id="08b72-113">Вызов функций</span><span class="sxs-lookup"><span data-stu-id="08b72-113">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="08b72-114">См. также</span><span class="sxs-lookup"><span data-stu-id="08b72-114">See Also</span></span>  
 [<span data-ttu-id="08b72-115">Mаршалинг строк</span><span class="sxs-lookup"><span data-stu-id="08b72-115">Marshaling Strings</span></span>](../../../docs/framework/interop/marshaling-strings.md)  
 [<span data-ttu-id="08b72-116">Типы данных вызовов неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="08b72-116">Platform Invoke Data Types</span></span>](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f)  
 [<span data-ttu-id="08b72-117">Маршалинг по умолчанию для строк</span><span class="sxs-lookup"><span data-stu-id="08b72-117">Default Marshaling for Strings</span></span>](../../../docs/framework/interop/default-marshaling-for-strings.md)  
 [<span data-ttu-id="08b72-118">Создание прототипов в управляемом коде</span><span class="sxs-lookup"><span data-stu-id="08b72-118">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="08b72-119">Определение кодировки</span><span class="sxs-lookup"><span data-stu-id="08b72-119">Specifying a Character Set</span></span>](../../../docs/framework/interop/specifying-a-character-set.md)

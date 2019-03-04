---
title: Как выполнить Проверка состояния подключения в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: bb3d5751ae7d88af05c2a77e9b64f9cb28179a35
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973019"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="867bf-102">Как выполнить Проверка состояния подключения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="867bf-102">How to: Check Connection Status in Visual Basic</span></span>
<span data-ttu-id="867bf-103">Свойство <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> можно использовать, чтобы проверить наличие на компьютере подключения к действующей сети или Интернету.</span><span class="sxs-lookup"><span data-stu-id="867bf-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="867bf-104">Проверка наличия на компьютере рабочего подключения</span><span class="sxs-lookup"><span data-stu-id="867bf-104">To check whether a computer has a working connection</span></span>  
  
-   <span data-ttu-id="867bf-105">Определите, имеет ли свойство `IsAvailable` значение `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="867bf-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="867bf-106">Следующий код проверяет состояние свойства и сообщает его:</span><span class="sxs-lookup"><span data-stu-id="867bf-106">The following code checks the property's status and reports it:</span></span>  
  
     [!code-vb[VbResourceTasks#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#3)]  
  
     <span data-ttu-id="867bf-107">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="867bf-107">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="867bf-108">В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**.</span><span class="sxs-lookup"><span data-stu-id="867bf-108">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="867bf-109">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="867bf-109">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="867bf-110">См. также</span><span class="sxs-lookup"><span data-stu-id="867bf-110">See also</span></span>
- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>

---
title: Практическое руководство. Проверка состояния подключения
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: 89ef431759dac25bd213fd954db0712ad95434b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345884"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="61c48-102">Практическое руководство. Проверка состояния подключения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="61c48-102">How to: Check Connection Status in Visual Basic</span></span>

<span data-ttu-id="61c48-103">Свойство <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> можно использовать, чтобы проверить наличие на компьютере подключения к действующей сети или Интернету.</span><span class="sxs-lookup"><span data-stu-id="61c48-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="61c48-104">Проверка наличия на компьютере рабочего подключения</span><span class="sxs-lookup"><span data-stu-id="61c48-104">To check whether a computer has a working connection</span></span>  
  
- <span data-ttu-id="61c48-105">Определите, имеет ли свойство `IsAvailable` значение `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="61c48-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="61c48-106">Следующий код проверяет состояние свойства и сообщает его:</span><span class="sxs-lookup"><span data-stu-id="61c48-106">The following code checks the property's status and reports it:</span></span>  
  
     [!code-vb[VbResourceTasks#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#3)]  
  
     <span data-ttu-id="61c48-107">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="61c48-107">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="61c48-108">В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**.</span><span class="sxs-lookup"><span data-stu-id="61c48-108">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="61c48-109">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="61c48-109">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c48-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="61c48-110">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>

---
title: Практическое руководство. Проверка состояния подключения в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: 1a03b181c2e363c3380c4f9858b629713641f2c2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620671"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="fe909-102">Практическое руководство. Проверка состояния подключения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fe909-102">How to: Check Connection Status in Visual Basic</span></span>
<span data-ttu-id="fe909-103">Свойство <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> можно использовать, чтобы проверить наличие на компьютере подключения к действующей сети или Интернету.</span><span class="sxs-lookup"><span data-stu-id="fe909-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="fe909-104">Проверка наличия на компьютере рабочего подключения</span><span class="sxs-lookup"><span data-stu-id="fe909-104">To check whether a computer has a working connection</span></span>  
  
- <span data-ttu-id="fe909-105">Определите, имеет ли свойство `IsAvailable` значение `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="fe909-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="fe909-106">Следующий код проверяет состояние свойства и сообщает его:</span><span class="sxs-lookup"><span data-stu-id="fe909-106">The following code checks the property's status and reports it:</span></span>  
  
     [!code-vb[VbResourceTasks#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#3)]  
  
     <span data-ttu-id="fe909-107">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="fe909-107">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="fe909-108">В средстве выбора фрагмента кода он расположен в разделе **Связь и сеть**.</span><span class="sxs-lookup"><span data-stu-id="fe909-108">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="fe909-109">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="fe909-109">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe909-110">См. также</span><span class="sxs-lookup"><span data-stu-id="fe909-110">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>

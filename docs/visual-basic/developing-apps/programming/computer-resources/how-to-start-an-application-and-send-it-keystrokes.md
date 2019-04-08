---
title: Практическое руководство. Запуск приложения и отправка ему нажатий клавиш (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: 9519fd85177d5d2adf97b54652c19330954edadf
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815970"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a><span data-ttu-id="14746-102">Практическое руководство. Запуск приложения и отправка ему нажатий клавиш (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14746-102">How to: Start an Application and Send it Keystrokes (Visual Basic)</span></span>
<span data-ttu-id="14746-103">В этом примере используется функция `Shell` для запуска приложения "Калькулятор", а затем перемножается два числа путем отправки событий нажатия клавиш с помощью метода `My.Computer.Keyboard.SendKeys`.</span><span class="sxs-lookup"><span data-stu-id="14746-103">This example uses the `Shell` function to start the calculator application and then multiplies two numbers by sending keystrokes using the `My.Computer.Keyboard.SendKeys` method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14746-104">Пример</span><span class="sxs-lookup"><span data-stu-id="14746-104">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]  
  
## <a name="robust-programming"></a><span data-ttu-id="14746-105">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="14746-105">Robust Programming</span></span>  
 <span data-ttu-id="14746-106">Если приложение с запрошенным идентификатором процесса не найдено, возникает исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="14746-106">A <xref:System.ArgumentException> exception is raised if an application with the requested process identifier cannot be found.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="14746-107">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="14746-107">.NET Framework Security</span></span>  
 <span data-ttu-id="14746-108">Вызов функции `Shell` требует полного доверия (класс <xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="14746-108">The call to the `Shell` function requires full trust (<xref:System.Security.SecurityException> class).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14746-109">См. также</span><span class="sxs-lookup"><span data-stu-id="14746-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>

---
title: Обработку событий пользовательского ввода в элементах управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: 19adeb6c803c76cba4139841f58087487d523a50
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739418"
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a><span data-ttu-id="68875-102">Практическое руководство. Обработка событий пользовательского ввода в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68875-102">How to: Handle User Input Events in Windows Forms Controls</span></span>
<span data-ttu-id="68875-103">В этом примере демонстрируется, как обрабатывать большинство событий клавиатуры, мыши, фокуса и проверки, которые происходят в элементе управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="68875-103">This example demonstrates how to handle most keyboard, mouse, focus, and validation events that can occur in a Windows Forms control.</span></span> <span data-ttu-id="68875-104">Текстовое поле с именем `TextBoxInput` получает события при установке в нем фокуса, и сведения о каждом событии записываются в текстовое поле с именем `TextBoxOutput` в том порядке, в котором вызываются события.</span><span class="sxs-lookup"><span data-stu-id="68875-104">The text box named `TextBoxInput` receives the events when it has focus, and information about each event is written in the text box named `TextBoxOutput` in the order in which the events are raised.</span></span> <span data-ttu-id="68875-105">В приложении также есть набор флажков, с помощью которых можно фильтровать события, о которых нужно сообщать.</span><span class="sxs-lookup"><span data-stu-id="68875-105">The application also includes a set of check boxes that can be used to filter which events to report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68875-106">Пример</span><span class="sxs-lookup"><span data-stu-id="68875-106">Example</span></span>  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="68875-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="68875-107">Compiling the Code</span></span>  
 <span data-ttu-id="68875-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="68875-108">This example requires:</span></span>  
  
- <span data-ttu-id="68875-109">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="68875-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68875-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="68875-110">See also</span></span>

- [<span data-ttu-id="68875-111">Ввод данных пользователем в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="68875-111">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)

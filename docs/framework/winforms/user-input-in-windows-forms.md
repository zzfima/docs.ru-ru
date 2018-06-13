---
title: Ввод данных пользователем в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard input [Windows Forms], using in Windows Forms
- Windows Forms, user input
- mouse input [Windows Forms], using in Windows Forms
- keyboards [Windows Forms], keyboard input
ms.assetid: 1486075f-1e06-4c9e-82c6-f948331db6d6
ms.openlocfilehash: 2a618dae8d5f2f5ea6a6581fff2758fe8419f511
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537737"
---
# <a name="user-input-in-windows-forms"></a><span data-ttu-id="8b679-102">Ввод данных пользователем в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b679-102">User Input in Windows Forms</span></span>
<span data-ttu-id="8b679-103">В Windows Forms включена модель ввода пользователя, основанная на событиях, которые возникают во время обработки соответствующих сообщений Windows.</span><span class="sxs-lookup"><span data-stu-id="8b679-103">Windows Forms includes a user input model based on events that are raised while processing related Windows messages.</span></span> <span data-ttu-id="8b679-104">Здесь приведены ссылки на разделы с информацией о вводе с помощью мыши и клавиатуры, включая примеры кода, демонстрирующие выполнение определенных задач.</span><span class="sxs-lookup"><span data-stu-id="8b679-104">The topics in this section provide information on mouse and keyboard user input, including code examples that demonstrate how to perform specific tasks.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b679-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="8b679-105">In This Section</span></span>  
 [<span data-ttu-id="8b679-106">Ввод данных пользователем в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b679-106">User Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/user-input-in-a-windows-forms-application.md)  
 <span data-ttu-id="8b679-107">Содержит обзор событий пользовательского ввода и методов, которые обрабатывают сообщения Windows.</span><span class="sxs-lookup"><span data-stu-id="8b679-107">Provides an overview of user input events and the methods that process Windows messages.</span></span>  
  
 [<span data-ttu-id="8b679-108">Ввод с клавиатуры в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b679-108">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 <span data-ttu-id="8b679-109">Содержит сведения об обработке сообщений клавиатуры, различных типах клавиш и событиях клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="8b679-109">Provides information on keyboard message handling, the different types of keys, and the keyboard events.</span></span>  
  
 [<span data-ttu-id="8b679-110">Ввод данных мышью в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b679-110">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)  
 <span data-ttu-id="8b679-111">Содержит сведения о событиях мыши и других связанных с мышью возможностях, включая курсоры и отслеживание перемещения мыши.</span><span class="sxs-lookup"><span data-stu-id="8b679-111">Provides information on the mouse events and other mouse-related features, including mouse cursors and mouse capture.</span></span>  
  
 [<span data-ttu-id="8b679-112">Практическое руководство. Имитация событий мыши и клавиатуры в коде</span><span class="sxs-lookup"><span data-stu-id="8b679-112">How to: Simulate Mouse and Keyboard Events in Code</span></span>](../../../docs/framework/winforms/how-to-simulate-mouse-and-keyboard-events-in-code.md)  
 <span data-ttu-id="8b679-113">Показано несколько различных способов программной имитации ввода с помощью мыши и клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="8b679-113">Demonstrates several different ways to programmatically simulate mouse and keyboard input.</span></span>  
  
 [<span data-ttu-id="8b679-114">Практическое руководство. Обработка событий пользовательского ввода в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b679-114">How to: Handle User Input Events in Windows Forms Controls</span></span>](../../../docs/framework/winforms/how-to-handle-user-input-events-in-windows-forms-controls.md)  
 <span data-ttu-id="8b679-115">Пример кода, который обрабатывает большую часть событий пользовательского ввода и сообщает сведения о каждом событии.</span><span class="sxs-lookup"><span data-stu-id="8b679-115">Presents a code example that handles most user input events and reports information about each event.</span></span>  
  
 [<span data-ttu-id="8b679-116">Проверка введенных пользователем данных в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b679-116">User Input Validation in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 <span data-ttu-id="8b679-117">Описываются методы проверки пользовательского ввода в приложениях Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="8b679-117">Describes the methods to validate user input in Windows Forms applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8b679-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="8b679-118">Related Sections</span></span>  
 <span data-ttu-id="8b679-119">См. также [Создание обработчиков событий в Windows Forms](http://msdn.microsoft.com/library/dacysss4\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="8b679-119">Also see [Creating Event Handlers in Windows Forms](http://msdn.microsoft.com/library/dacysss4\(v=vs.110\)).</span></span>

---
title: Практическое руководство. Изменение ввода с клавиатуры в стандартном элементе управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboard input [Windows Forms], modifying
- modifying keyboard input
- Windows Forms, modifying keyboard input
- keyboards [Windows Forms], keyboard input
ms.assetid: 626d3712-d866-4988-bcda-a2d5b36ec0ba
ms.openlocfilehash: 8ac04a94fb567afa184172c0685438e26834fe5b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589234"
---
# <a name="how-to-modify-keyboard-input-to-a-standard-control"></a><span data-ttu-id="7a9af-102">Практическое руководство. Изменение ввода с клавиатуры в стандартном элементе управления</span><span class="sxs-lookup"><span data-stu-id="7a9af-102">How to: Modify Keyboard Input to a Standard Control</span></span>
<span data-ttu-id="7a9af-103">Формы Windows Forms предоставляют возможность получать и изменять вводимые с клавиатуры данные.</span><span class="sxs-lookup"><span data-stu-id="7a9af-103">Windows Forms provides the ability to consume and modify keyboard input.</span></span> <span data-ttu-id="7a9af-104">Получением клавиши называется обработка клавиши внутри метода или обработчика событий таким образом, чтобы следующие методы и события в очереди сообщений не получали значение этой клавиши.</span><span class="sxs-lookup"><span data-stu-id="7a9af-104">Consuming a key refers to handling a key within a method or event handler so that other methods and events further down the message queue do not receive the key value.</span></span> <span data-ttu-id="7a9af-105">Изменением клавиши называется изменение значения клавиши таким образом, чтобы следующие методы и обработчики событий в очереди сообщений получали другое значение клавиши.</span><span class="sxs-lookup"><span data-stu-id="7a9af-105">Modifying a key refers to modifying the value of a key so that methods and event handlers further down the message queue receive a different key value.</span></span> <span data-ttu-id="7a9af-106">В этом разделе показано, как выполнять эти задачи.</span><span class="sxs-lookup"><span data-stu-id="7a9af-106">This topic shows how to accomplish these tasks.</span></span>  
  
### <a name="to-consume-a-key"></a><span data-ttu-id="7a9af-107">Получение клавиши</span><span class="sxs-lookup"><span data-stu-id="7a9af-107">To consume a key</span></span>  
  
- <span data-ttu-id="7a9af-108">В обработчике событий <xref:System.Windows.Forms.Control.KeyPress> установите для свойства <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> класса <xref:System.Windows.Forms.KeyPressEventArgs> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7a9af-108">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to `true`.</span></span>  
  
     <span data-ttu-id="7a9af-109">-или-</span><span class="sxs-lookup"><span data-stu-id="7a9af-109">-or-</span></span>  
  
     <span data-ttu-id="7a9af-110">В обработчике событий <xref:System.Windows.Forms.Control.KeyDown> установите для свойства <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> класса <xref:System.Windows.Forms.KeyEventArgs> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7a9af-110">In a <xref:System.Windows.Forms.Control.KeyDown> event handler, set the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> class to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a9af-111">Установка свойства <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> в обработчике событий <xref:System.Windows.Forms.Control.KeyDown> не препятствует возникновению событий <xref:System.Windows.Forms.Control.KeyPress> и <xref:System.Windows.Forms.Control.KeyUp> для текущей клавиши.</span><span class="sxs-lookup"><span data-stu-id="7a9af-111">Setting the <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> property in the <xref:System.Windows.Forms.Control.KeyDown> event handler does not prevent the <xref:System.Windows.Forms.Control.KeyPress> and <xref:System.Windows.Forms.Control.KeyUp> events from being raised for the current keystroke.</span></span> <span data-ttu-id="7a9af-112">Для этой цели используется свойство <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A>.</span><span class="sxs-lookup"><span data-stu-id="7a9af-112">Use the <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A> property for this purpose.</span></span>  
  
     <span data-ttu-id="7a9af-113">В примере ниже показан фрагмент кода оператора `switch`, который проверяет свойство <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> класса <xref:System.Windows.Forms.KeyPressEventArgs>, полученное обработчиком событий <xref:System.Windows.Forms.Control.KeyPress>.</span><span class="sxs-lookup"><span data-stu-id="7a9af-113">The following example is an excerpt from a `switch` statement that examines the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> received by a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span> <span data-ttu-id="7a9af-114">Этот код получает клавиши со знаками "A" и "a".</span><span class="sxs-lookup"><span data-stu-id="7a9af-114">This code consumes the 'A' and 'a' character keys.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#6)]  
  
### <a name="to-modify-a-standard-character-key"></a><span data-ttu-id="7a9af-115">Изменение стандартной символьной клавиши</span><span class="sxs-lookup"><span data-stu-id="7a9af-115">To modify a standard character key</span></span>  
  
- <span data-ttu-id="7a9af-116">В обработчике событий <xref:System.Windows.Forms.Control.KeyPress> задайте для свойства <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> класса <xref:System.Windows.Forms.KeyPressEventArgs> значение новой символьной клавиши.</span><span class="sxs-lookup"><span data-stu-id="7a9af-116">In a <xref:System.Windows.Forms.Control.KeyPress> event handler, set the <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> class to the value of the new character key.</span></span>  
  
     <span data-ttu-id="7a9af-117">В примере ниже показан фрагмент кода оператора `switch`, изменяющего клавиши "B" на "A" и "b" на "a".</span><span class="sxs-lookup"><span data-stu-id="7a9af-117">The following example is an excerpt from a `switch` statement that modifies 'B' to 'A' and 'b' to 'a'.</span></span> <span data-ttu-id="7a9af-118">Следует отметить, что для свойства <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> параметра <xref:System.Windows.Forms.KeyPressEventArgs> установлено значение `false`, чтобы новое значение клавиши передавалось другим методам и событиям в очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="7a9af-118">Note that the <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> property of the <xref:System.Windows.Forms.KeyPressEventArgs> parameter is set to `false`, so that the new key value is propagated to other methods and events in the message queue.</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#7)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#7)]  
  
### <a name="to-modify-a-noncharacter-key"></a><span data-ttu-id="7a9af-119">Изменение клавиши, не связанной со знаком</span><span class="sxs-lookup"><span data-stu-id="7a9af-119">To modify a noncharacter key</span></span>  
  
- <span data-ttu-id="7a9af-120">Переопределите метод <xref:System.Windows.Forms.Control>, который обрабатывает сообщения Windows, найдите сообщение WM_KEYDOWN или WM_SYSKEYDOWN и установите для свойства <xref:System.Windows.Forms.Message.WParam%2A> параметра <xref:System.Windows.Forms.Message> значение <xref:System.Windows.Forms.Keys>, представляющее новую клавишу, не связанную со знаком.</span><span class="sxs-lookup"><span data-stu-id="7a9af-120">Override a <xref:System.Windows.Forms.Control> method that processes Windows messages, detect the WM_KEYDOWN or WM_SYSKEYDOWN message, and set the <xref:System.Windows.Forms.Message.WParam%2A> property of the <xref:System.Windows.Forms.Message> parameter to the <xref:System.Windows.Forms.Keys> value that represents the new noncharacter key.</span></span>  
  
     <span data-ttu-id="7a9af-121">В примере кода ниже показано, как переопределить метод <xref:System.Windows.Forms.Control.PreProcessMessage%2A> элемента управления для обнаружения клавиш с F1 по F9 и изменения нажатия клавиши F3 на F1.</span><span class="sxs-lookup"><span data-stu-id="7a9af-121">The following code example demonstrates how to override the <xref:System.Windows.Forms.Control.PreProcessMessage%2A> method of a control to detect keys F1 through F9 and modify any F3 key press to F1.</span></span> <span data-ttu-id="7a9af-122">Дополнительные сведения о <xref:System.Windows.Forms.Control> методы, которые можно переопределить для перехвата сообщений клавиатуры, см. в разделе [ввод данных пользователем в приложении Windows Forms](user-input-in-a-windows-forms-application.md) и [принцип работы ввода с клавиатуры](how-keyboard-input-works.md).</span><span class="sxs-lookup"><span data-stu-id="7a9af-122">For more information on <xref:System.Windows.Forms.Control> methods that you can override to intercept keyboard messages, see [User Input in a Windows Forms Application](user-input-in-a-windows-forms-application.md) and [How Keyboard Input Works](how-keyboard-input-works.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="7a9af-123">Пример</span><span class="sxs-lookup"><span data-stu-id="7a9af-123">Example</span></span>  
 <span data-ttu-id="7a9af-124">В примере ниже полностью представлено приложение для примеров кода из предыдущих разделов.</span><span class="sxs-lookup"><span data-stu-id="7a9af-124">The following code example is the complete application for the code examples in the previous sections.</span></span> <span data-ttu-id="7a9af-125">Для получения и изменения вводимых с клавиатуры данных в приложении используется пользовательский элемент управления, производный от класса <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="7a9af-125">The application uses a custom control derived from the <xref:System.Windows.Forms.TextBox> class to consume and modify keyboard input.</span></span>  
  
 [!code-csharp[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInput#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7a9af-126">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="7a9af-126">Compiling the Code</span></span>  
 <span data-ttu-id="7a9af-127">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="7a9af-127">This example requires:</span></span>  
  
- <span data-ttu-id="7a9af-128">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="7a9af-128">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a9af-129">См. также</span><span class="sxs-lookup"><span data-stu-id="7a9af-129">See also</span></span>

- [<span data-ttu-id="7a9af-130">Ввод с клавиатуры в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a9af-130">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="7a9af-131">Ввод данных пользователем в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7a9af-131">User Input in a Windows Forms Application</span></span>](user-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="7a9af-132">Принцип работы ввода с клавиатуры</span><span class="sxs-lookup"><span data-stu-id="7a9af-132">How Keyboard Input Works</span></span>](how-keyboard-input-works.md)

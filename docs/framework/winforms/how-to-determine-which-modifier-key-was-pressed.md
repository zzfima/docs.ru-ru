---
title: Практическое руководство. Определение нажатой управляющей клавиши
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: 1c89149fc07f89028b21fa513fd84dee4e890968
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540021"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="1ae01-102">Практическое руководство. Определение нажатой управляющей клавиши</span><span class="sxs-lookup"><span data-stu-id="1ae01-102">How to: Determine Which Modifier Key Was Pressed</span></span>
<span data-ttu-id="1ae01-103">При создании приложения, которое принимает пользователя нажатия клавиш, можно также для наблюдения за нажатием клавиш SHIFT, ALT и CTRL ключи.</span><span class="sxs-lookup"><span data-stu-id="1ae01-103">When you create an application that accepts the user's keystrokes, you may also want to monitor for modifier keys such as the SHIFT, ALT, and CTRL keys.</span></span> <span data-ttu-id="1ae01-104">При нажатии клавиши-модификатора в сочетании с другими ключами или нажатием кнопки мыши, приложение может реагировать соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="1ae01-104">When a modifier key is pressed in combination with other keys, or with mouse clicks, your application can respond appropriately.</span></span> <span data-ttu-id="1ae01-105">Например если нажата буквы S, это может вызвать просто «s» для отображения на экране, но при нажатии клавиш CTRL + S, текущий документ может быть сохранен.</span><span class="sxs-lookup"><span data-stu-id="1ae01-105">For example, if the letter S is pressed, this may simply cause an "s" to appear on the screen, but if the keys CTRL+S are pressed, the current document may be saved.</span></span> <span data-ttu-id="1ae01-106">При обработке <xref:System.Windows.Forms.Control.KeyDown> событий, <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> свойство <xref:System.Windows.Forms.KeyEventArgs> полученных событием обработчик определяет, при нажатии клавиши-модификаторы.</span><span class="sxs-lookup"><span data-stu-id="1ae01-106">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="1ae01-107">Кроме того <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> свойство <xref:System.Windows.Forms.KeyEventArgs> определяет символ, который в сочетании с побитового или с любыми клавиши-модификаторы также была нажата.</span><span class="sxs-lookup"><span data-stu-id="1ae01-107">Alternatively, the <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property of <xref:System.Windows.Forms.KeyEventArgs> specifies the character that was pressed as well as any modifier keys combined with a bitwise OR.</span></span> <span data-ttu-id="1ae01-108">Тем не менее если обрабатывается <xref:System.Windows.Forms.Control.KeyPress> событие или событие мыши, обработчик событий не получает эти сведения.</span><span class="sxs-lookup"><span data-stu-id="1ae01-108">However, if you are handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler does not receive this information.</span></span> <span data-ttu-id="1ae01-109">В этом случае необходимо использовать <xref:System.Windows.Forms.Control.ModifierKeys%2A> свойство <xref:System.Windows.Forms.Control> класса.</span><span class="sxs-lookup"><span data-stu-id="1ae01-109">In this case, you must use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="1ae01-110">В любом случае необходимо выполнить операцию побитового и соответствующего <xref:System.Windows.Forms.Keys> значения и тестировании.</span><span class="sxs-lookup"><span data-stu-id="1ae01-110">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you are testing.</span></span> <span data-ttu-id="1ae01-111"><xref:System.Windows.Forms.Keys> Перечисление предоставляет варианты каждого ключа модификатор, поэтому важно выполнения битовой операции и правильное значение.</span><span class="sxs-lookup"><span data-stu-id="1ae01-111">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it is important that you perform the bitwise AND with the correct value.</span></span> <span data-ttu-id="1ae01-112">Например, клавиша SHIFT представляется <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> и <xref:System.Windows.Forms.Keys.LShiftKey> правильное значение для тестирования является клавиша SHIFT <xref:System.Windows.Forms.Keys.Shift>.</span><span class="sxs-lookup"><span data-stu-id="1ae01-112">For example, the SHIFT key is represented by <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> and <xref:System.Windows.Forms.Keys.LShiftKey> The correct value to test SHIFT as a modifier key is <xref:System.Windows.Forms.Keys.Shift>.</span></span> <span data-ttu-id="1ae01-113">Аналогичным образом, для проверки CTLR и ALT как модификаторы вы должны использовать <xref:System.Windows.Forms.Keys.Control> и <xref:System.Windows.Forms.Keys.Alt> соответственно.</span><span class="sxs-lookup"><span data-stu-id="1ae01-113">Similarly, to test for CTLR and ALT as modifiers you should use the <xref:System.Windows.Forms.Keys.Control> and <xref:System.Windows.Forms.Keys.Alt> values, respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ae01-114">Программисты на Visual Basic могут просматривать ключевые данные через <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> свойство</span><span class="sxs-lookup"><span data-stu-id="1ae01-114">Visual Basic programmers can also access key information through the <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> property</span></span>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="1ae01-115">Для определения нажатой управляющей клавиши</span><span class="sxs-lookup"><span data-stu-id="1ae01-115">To determine which modifier key was pressed</span></span>  
  
-   <span data-ttu-id="1ae01-116">Используйте побитовый `AND` оператор с <xref:System.Windows.Forms.Control.ModifierKeys%2A> свойство и значение <xref:System.Windows.Forms.Keys> enumeration, чтобы определить, нажата ли определенной клавиши.</span><span class="sxs-lookup"><span data-stu-id="1ae01-116">Use the bitwise `AND` operator with the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and a value of the <xref:System.Windows.Forms.Keys> enumeration to determine whether a particular modifier key is pressed.</span></span> <span data-ttu-id="1ae01-117">В следующем примере кода показано, как определить, является ли нажата клавиша SHIFT, внутри <xref:System.Windows.Forms.Control.KeyPress> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="1ae01-117">The following code example shows how to determine whether the SHIFT key is pressed within a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="1ae01-118">См. также</span><span class="sxs-lookup"><span data-stu-id="1ae01-118">See Also</span></span>  
 <xref:System.Windows.Forms.Keys>  
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>  
 [<span data-ttu-id="1ae01-119">Ввод с клавиатуры в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1ae01-119">Keyboard Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [<span data-ttu-id="1ae01-120">Как: определить ли CapsLock на Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1ae01-120">How to: Determine If CapsLock is On in Visual Basic</span></span>](http://msdn.microsoft.com/library/91e60f5c-dd61-4222-ba5f-39af803afd8c)

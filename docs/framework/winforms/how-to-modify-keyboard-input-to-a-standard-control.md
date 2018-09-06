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
ms.openlocfilehash: c109615b9a0eb61d18f7f44e3248d2b24934ee5f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43787159"
---
# <a name="how-to-modify-keyboard-input-to-a-standard-control"></a>Практическое руководство. Изменение ввода с клавиатуры в стандартном элементе управления
Формы Windows Forms предоставляют возможность получать и изменять вводимые с клавиатуры данные. Получением клавиши называется обработка клавиши внутри метода или обработчика событий таким образом, чтобы следующие методы и события в очереди сообщений не получали значение этой клавиши. Изменением клавиши называется изменение значения клавиши таким образом, чтобы следующие методы и обработчики событий в очереди сообщений получали другое значение клавиши. В этом разделе показано, как выполнять эти задачи.  
  
### <a name="to-consume-a-key"></a>Получение клавиши  
  
-   В обработчике событий <xref:System.Windows.Forms.Control.KeyPress> установите для свойства <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> класса <xref:System.Windows.Forms.KeyPressEventArgs> значение `true`.  
  
     -или-  
  
     В обработчике событий <xref:System.Windows.Forms.Control.KeyDown> установите для свойства <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> класса <xref:System.Windows.Forms.KeyEventArgs> значение `true`.  
  
    > [!NOTE]
    >  Установка свойства <xref:System.Windows.Forms.KeyEventArgs.Handled%2A> в обработчике событий <xref:System.Windows.Forms.Control.KeyDown> не препятствует возникновению событий <xref:System.Windows.Forms.Control.KeyPress> и <xref:System.Windows.Forms.Control.KeyUp> для текущей клавиши. Для этой цели используется свойство <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A>.  
  
     В примере ниже показан фрагмент кода оператора `switch`, который проверяет свойство <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> класса <xref:System.Windows.Forms.KeyPressEventArgs>, полученное обработчиком событий <xref:System.Windows.Forms.Control.KeyPress>. Этот код получает клавиши со знаками "A" и "a".  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#6](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#6](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#6)]  
  
### <a name="to-modify-a-standard-character-key"></a>Изменение стандартной символьной клавиши  
  
-   В обработчике событий <xref:System.Windows.Forms.Control.KeyPress> задайте для свойства <xref:System.Windows.Forms.KeyPressEventArgs.KeyChar%2A> класса <xref:System.Windows.Forms.KeyPressEventArgs> значение новой символьной клавиши.  
  
     В примере ниже показан фрагмент кода оператора `switch`, изменяющего клавиши "B" на "A" и "b" на "a". Следует отметить, что для свойства <xref:System.Windows.Forms.KeyPressEventArgs.Handled%2A> параметра <xref:System.Windows.Forms.KeyPressEventArgs> установлено значение `false`, чтобы новое значение клавиши передавалось другим методам и событиям в очереди сообщений.  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#7](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#7)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#7](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#7)]  
  
### <a name="to-modify-a-noncharacter-key"></a>Изменение клавиши, не связанной со знаком  
  
-   Переопределите метод <xref:System.Windows.Forms.Control>, который обрабатывает сообщения Windows, найдите сообщение WM_KEYDOWN или WM_SYSKEYDOWN и установите для свойства <xref:System.Windows.Forms.Message.WParam%2A> параметра <xref:System.Windows.Forms.Message> значение <xref:System.Windows.Forms.Keys>, представляющее новую клавишу, не связанную со знаком.  
  
     В примере кода ниже показано, как переопределить метод <xref:System.Windows.Forms.Control.PreProcessMessage%2A> элемента управления для обнаружения клавиш с F1 по F9 и изменения нажатия клавиши F3 на F1. Дополнительные сведения о <xref:System.Windows.Forms.Control> методы, которые можно переопределить для перехвата сообщений клавиатуры, см. в разделе [ввод данных пользователем в приложении Windows Forms](../../../docs/framework/winforms/user-input-in-a-windows-forms-application.md) и [принцип работы ввода с клавиатуры](../../../docs/framework/winforms/how-keyboard-input-works.md).  
  
     [!code-csharp[System.Windows.Forms.KeyBoardInput#12](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#12)]
     [!code-vb[System.Windows.Forms.KeyBoardInput#12](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#12)]  
  
## <a name="example"></a>Пример  
 В примере ниже полностью представлено приложение для примеров кода из предыдущих разделов. Для получения и изменения вводимых с клавиатуры данных в приложении используется пользовательский элемент управления, производный от класса <xref:System.Windows.Forms.TextBox>.  
  
 [!code-csharp[System.Windows.Forms.KeyBoardInput#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.KeyBoardInput#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyboardInput/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
 Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 [Ввод с клавиатуры в приложении Windows Forms](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Ввод данных пользователем в приложении Windows Forms](../../../docs/framework/winforms/user-input-in-a-windows-forms-application.md)  
 [Принцип работы ввода с клавиатуры](../../../docs/framework/winforms/how-keyboard-input-works.md)

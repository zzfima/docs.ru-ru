---
title: Реагирование на изменения шрифтовой схемы в приложении Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: e3b96139a7cfd4b268d81b1da58229527e2beb87
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739226"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a>Практическое руководство. Реагирование на изменения схемы шрифтов в приложениях Windows Forms
В операционных системах Windows пользователь может изменить параметры шрифта в масштабе всей системы, сделав шрифт по умолчанию больше или меньше. Изменение этих параметров шрифта является критически важным для пользователей, имеющих визуальное нарушение, и требует большего размера для чтения текста на своих экранах. Можно настроить приложение Windows Forms для реагирования на эти изменения, увеличивая или уменьшая размер формы и весь содержащийся в ней текст при изменении шрифтовой схемы. Если требуется, чтобы форма автоматически соответствовала изменениям размеров шрифтов, можно добавить код в форму.  
  
 Как правило, шрифтом по умолчанию, используемым Windows Forms, является шрифт, возвращаемый вызовом пространства имен <xref:Microsoft.Win32> в `GetStockObject(DEFAULT_GUI_FONT)`. Шрифт, возвращаемый этим вызовом, изменяется только при изменении разрешения экрана. Как показано в следующей процедуре, код должен изменить шрифт по умолчанию на <xref:System.Drawing.SystemFonts.IconTitleFont%2A>, чтобы реагировать на изменения размера шрифта.  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a>Использование шрифта рабочего стола и реагирование на изменения схемы шрифтов  
  
1. Создайте форму и добавьте в нее нужные элементы управления. Дополнительные сведения см. в разделе [инструкции. создание Windows Forms приложения из командной строки](how-to-create-a-windows-forms-application-from-the-command-line.md) и [элементов управления для использования в Windows Forms](./controls/controls-to-use-on-windows-forms.md).  
  
2. Добавьте ссылку на пространство имен <xref:Microsoft.Win32> в код.  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. Добавьте следующий код в конструктор формы, чтобы подключить необходимые обработчики событий и изменить используемый по умолчанию шрифт для формы.  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. Реализуйте обработчик для события <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>, которое приводит к автоматическому масштабированию формы при изменении категории <xref:Microsoft.Win32.UserPreferenceCategory.Window>.  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. Наконец, реализуйте обработчик для события <xref:System.Windows.Forms.Form.FormClosing>, которое отсоединяет обработчик событий <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.  
  
     > [!IMPORTANT]
     > Сбой включения этого кода приведет к утечке памяти в приложении.  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. Скомпилируйте и запустите код.  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a>Изменение схемы шрифтов в Windows XP вручную  
  
1. Пока приложение Windows Forms работает, щелкните правой кнопкой мыши рабочий стол Windows и выберите в контекстном меню пункт **Свойства** .  
  
2. В диалоговом окне **Свойства экрана** перейдите на вкладку **вид** .  
  
3. В раскрывающемся списке **Размер шрифта** выберите новый размер шрифта.  
  
     Обратите внимание, что форма теперь реагирует на изменения, внесенные во время выполнения в шрифтовую схему рабочего стола. При изменении пользователем между **обычными**, **крупными шрифтами**и **очень крупными шрифтами**форма изменяет шрифт и масштабируется правильно.  
  
## <a name="example"></a>Пример  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 Конструктор в этом примере кода содержит вызов `InitializeComponent`, который определяется при создании нового проекта Windows Forms в Visual Studio. Удалите эту строку кода, если вы создаете приложение в командной строке.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [Автоматическое масштабирование в Windows Forms](automatic-scaling-in-windows-forms.md)

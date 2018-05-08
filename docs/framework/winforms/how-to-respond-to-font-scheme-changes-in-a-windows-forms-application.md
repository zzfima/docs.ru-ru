---
title: Практическое руководство. Реагирование на изменения схемы шрифтов в приложениях Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 455609ea602f450803718f5be34618b087560d21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a>Практическое руководство. Реагирование на изменения схемы шрифтов в приложениях Windows Forms
В операционных системах Windows пользователь может изменить параметры шрифта во всей системе, чтобы проверить шрифт по умолчанию отображаются, больше или меньше. Изменение этих параметров шрифтов особенно важно для пользователей с нарушениями зрения и требуется больший тип для чтения текста на экране компьютера. Можно настроить приложение Windows Forms реагировать на изменения путем увеличения или уменьшения размера формы и все содержащиеся в нем текста при каждом изменении шрифтовой схемы. Если вы хотите формы в соответствии с изменением размеров шрифта динамически, можно добавить код в форму.  
  
 Как правило, шрифт по умолчанию, используемые в Windows Forms используется шрифт, возвращенных <xref:Microsoft.Win32> вызов пространства имен `GetStockObject(DEFAULT_GUI_FONT)`. Шрифт, возвращаемый при вызове этого метода изменяется только при изменении разрешения экрана. Как показано в следующей процедуре, ваш код должен изменить шрифт по умолчанию для <xref:System.Drawing.SystemFonts.IconTitleFont%2A> реагировать на изменения размера шрифта.  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a>Чтобы использовать шрифт рабочего стола и реагировать на изменения схемы шрифтов  
  
1.  Создайте форму и добавить элементы управления, которые вы хотите его. Дополнительные сведения см. в разделе [как: Создание приложения Windows Forms из командной строки](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) и [элементы управления для использования в формах Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).  
  
2.  Добавьте ссылку на <xref:Microsoft.Win32> пространства имен в код.  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  Добавьте следующий код в конструктор формы для подключения необходимых обработчиков событий и изменить шрифт по умолчанию для данной формы.  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  Реализуйте обработчик для <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> событие, которое приводит к автоматическому масштабированию формы при <xref:Microsoft.Win32.UserPreferenceCategory.Window> категории изменений.  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  Наконец, Реализуйте обработчик <xref:System.Windows.Forms.Form.FormClosing> событие, отсоединяет <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> обработчика событий.  
  
> [!IMPORTANT]
>  Если не добавить этот код вызовет утечка памяти.  
  
 [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
 [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
1.  Скомпилируйте и запустите код.  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a>Чтобы вручную изменить схему шрифта в Windows XP  
  
1.  Во время работы приложения Windows Forms, щелкните правой кнопкой мыши рабочий стол Windows и выберите **свойства** в контекстном меню.  
  
2.  В **свойства отображения** диалоговое окно, нажмите кнопку **внешний вид** вкладки.  
  
3.  Из **размер шрифта** раскрывающемся списке выберите новый размер шрифта.  
  
     Обратите внимание, что форма теперь реагирует для запуска время изменения схемы шрифтов рабочего стола. Когда пользователь изменяет между **обычный**, **крупный шрифт**, и **Огромный шрифт**, форма изменяет шрифт и корректно масштабируется.  
  
## <a name="example"></a>Пример  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 Конструктор в этом примере код содержит вызов `InitializeComponent`, который определяется при создании нового проекта Windows Forms в Visual Studio. Удалите эту строку кода при построении приложения в командной строке.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>  
 [Автоматическое масштабирование в Windows Forms](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)

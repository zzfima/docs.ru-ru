---
title: "How to: Respond to Font Scheme Changes in a Windows Forms Application | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, font scheme changes"
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Respond to Font Scheme Changes in a Windows Forms Application
В операционных системах Windows пользователь может изменить параметры шрифтов на уровне системы, чтобы увеличить или уменьшить размер шрифта, отображаемого по умолчанию.  Изменение этих параметров шрифтов особенно важно для пользователей с нарушениями зрения, которые нуждаются в большом размере шрифта при чтении текста с экрана.  Приложение Windows Forms можно настроить так, чтобы при каждом изменении шрифтовой схемы, оно реагировало на эти изменения увеличением или уменьшением размера формы и всего содержащегося текста.  Если требуется, чтобы форма приспосабливалась к изменениям размера шрифта динамически, то можно добавить в форму соответствующий код.  
  
 Как правило, формами Windows Forms используется шрифт по умолчанию, который возвращается при вызове метода `GetStockObject(DEFAULT_GUI_FONT)` пространства имен <xref:Microsoft.Win32>.  Шрифт, возвращаемый при вызове этого метода, изменяется только при изменении разрешения экрана.  Как показано в следующей процедуре, ваш код должен изменить шрифт по умолчанию для <xref:System.Drawing.SystemFonts.IconTitleFont%2A> в ответ на изменение размера шрифта.  
  
### Чтобы использовать шрифт рабочего стола и реагировать на изменения шрифтовой схемы, выполните следующие действия.  
  
1.  Создайте форму и добавьте в нее требуемые элементы управления.  Дополнительные сведения см. в разделах [How to: Create a Windows Forms Application from the Command Line](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) и [Элементы управления для использования в формах Windows Forms](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).  
  
2.  Добавьте в код ссылку на пространство имен <xref:Microsoft.Win32>.  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  Добавьте следующий код в конструктор формы для подключения необходимых обработчиков событий и изменения шрифта по умолчанию для данной формы.  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  Реализуйте обработчик события <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>, который приводит к автоматическому масштабированию формы при изменении категории <xref:Microsoft.Win32.UserPreferenceCategory>.  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  Наконец, реализуйте обработчик события <xref:System.Windows.Forms.Form.FormClosing>, который отсоединяет обработчик событий <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.  
  
> [!IMPORTANT]
>  Если не добавить этот код, произойдет утечка памяти.  
  
 [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
 [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
1.  Скомпилируйте и запустите код.  
  
### Чтобы вручную изменить шрифтовую схему в Windows XP, выполните следующие действия.  
  
1.  Во время работы приложения Windows Forms щелкните правой кнопкой мыши рабочий стол Windows и выберите **Свойства** в контекстном меню.  
  
2.  В диалоговом окне **Свойства: Экран** перейдите на вкладку **Вид**.  
  
3.  Из раскрывающегося списка **Размер шрифта** выберите новый размер шрифта.  
  
     Обратите внимание, что форма теперь реагирует на изменения схемы шрифтов рабочего стола во время выполнения.  Когда пользователь переключается между значениями **Обычный**, **Крупный шрифт** и **Огромный шрифт**, форма изменяет шрифт и корректно масштабируется.  
  
## Пример  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 Конструктор в этом примере кода содержит вызов метода `InitializeComponent`, который определен при создании нового проекта Windows Forms в Visual Studio.  Удалите эту строку кода при построении приложения из командной строки.  
  
## См. также  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>   
 [Automatic Scaling in Windows Forms](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)
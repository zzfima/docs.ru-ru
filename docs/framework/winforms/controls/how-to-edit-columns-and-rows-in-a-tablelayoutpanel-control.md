---
title: "Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "net.ComponentModel.StyleCollectionEditor"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "столбцы [Windows Forms], редактирование"
  - "строки [Windows Forms], редактирование"
  - "TableLayoutPanel - элемент управления [Windows Forms], редактирование"
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel
Можно использовать редактор коллекций элемента управления <xref:System.Windows.Forms.TableLayoutPanel>, называемый диалоговым окном **Стили столбцов и строк**, для редактирования строк и столбцов элементов управления.  
  
> [!NOTE]
>  Чтобы элемент управления объединял несколько строк или столбцов задайте для элемента управления свойства `RowSpan` и `ColumnSpan`.  Дополнительные сведения см. в разделе [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Чтобы выровнять или растянуть элемент управления внутри ячейки, используйте свойство <xref:System.Windows.Forms.Control.Anchor%2A> элемента управления.  Дополнительные сведения см. в разделе [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы редактировать столбцы и строки  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в форму.  
  
2.  Щелкните глиф смарт\-тега для элемента управления <xref:System.Windows.Forms.TableLayoutPanel> \(![Глиф смарт&#45;тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) и выберите команду **Редактировать строки и столбцы**, чтобы открыть диалоговое окно **Стили столбцов и строк**.  Можно также щелкнуть правой кнопкой мыши по элементу управления <xref:System.Windows.Forms.TableLayoutPanel> и выбрать из раскрывающегося меню команду **Редактировать строки и столбцы**.  
  
3.  Чтобы добавить или удалить столбцы выберите из раскрывающегося списка **Тип члена** элемент **Столбцы**.  
  
4.  Чтобы добавить или удалить строки выберите из раскрывающегося списка **Тип члена** элемент **Строки**.  
  
5.  Нажмите кнопку **Добавить** для добавления строки или столбцы в конец списка **Член**.  
  
6.  Нажмите кнопку **Вставить** для добавления строки или столбца перед выделенным элементом списка.  
  
7.  При добавлении строки или столбца выберите **Тип размера** для новой строки или столбца.  Дополнительные сведения см. в разделе <xref:System.Windows.Forms.SizeType>.  
  
8.  Для удаления строки или столбца нажмите кнопку **Удалить** для удаления выделенного элемента в списке **Член**.  
  
## См. также  
 <xref:System.Windows.Forms.SizeType>   
 [Элемент управления TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
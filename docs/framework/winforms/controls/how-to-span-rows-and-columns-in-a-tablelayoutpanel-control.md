---
title: "Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel | Microsoft Docs"
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
  - "net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ячейки, слияние"
  - "столбцы [Windows Forms], объединение"
  - "объединение ячеек"
  - "строки [Windows Forms], объединение"
  - "TableLayoutPanel - элемент управления [Windows Forms], объединение строк и столбцов"
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel
Элементы управления в элементе управления <xref:System.Windows.Forms.TableLayoutPanel> могут объединять соседние строки и столбцы.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы объединить столбцы и строки  
  
1.  Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в форму.  
  
2.  Перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в верхнюю левую ячейку элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
3.  Присвойте свойству **ColumnSpan** элемента управления <xref:System.Windows.Forms.Button> значение 2.  Обратите внимание, что элемент управления <xref:System.Windows.Forms.Button> теперь относится к первому и второму столбцам.  
  
4.  Присвойте свойству **RowSpan** элемента управления <xref:System.Windows.Forms.Button> значение 2.  Обратите внимание, что элемент управления <xref:System.Windows.Forms.Button> теперь относится к первой и второй строкам.  
  
5.  Присвойте свойству **ColumnSpan** элемента управления <xref:System.Windows.Forms.Button> значение 1.  Обратите внимание, что элемент управления <xref:System.Windows.Forms.Button> перемещается в первый столбец, но охватывает первую и вторую строку.  
  
## См. также  
 [Элемент управления TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
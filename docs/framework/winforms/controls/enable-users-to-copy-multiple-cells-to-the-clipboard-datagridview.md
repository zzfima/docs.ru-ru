---
title: "Практическое руководство. Разрешение копирования в буфер обмена нескольких ячеек элемента управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ячейки, копирование в буфер обмена"
  - "буфер обмена, копирование нескольких ячеек"
  - "таблицы данных, копирование нескольких ячеек"
  - "DataGridView - элемент управления [Windows Forms], копирование нескольких ячеек"
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Разрешение копирования в буфер обмена нескольких ячеек элемента управления DataGridView в Windows Forms
При включении копирования ячеек данные в элементе управления <xref:System.Windows.Forms.DataGridView> становятся доступны для других приложений с помощью <xref:System.Windows.Forms.Clipboard>.  Значения выделенных ячеек преобразуются в строки и добавляются в буфер обмена в виде значений, разделенных символами табуляции, для вставки в такие приложения, как "Блокнот" или Excel, и в виде таблицы в формате HTML для вставки в такие приложения, как Microsoft Word.  
  
 Можно настроить копирование ячеек, чтобы копировать только значения ячеек, включить текст заголовка строки и столбца в данные буфера обмена или включать текст заголовка только в том случае, когда пользователь выбирает все строки или столбцы.  
  
 В зависимости от режима выделения пользователи могут выбрать несколько разрозненных групп ячеек.  При копировании ячеек в буфер обмена строки и столбцы, не имеющие выделенных ячеек, не копируются.  Все строки или столбцы становятся строками и столбцами в таблице данных, скопированной в буфер обмена.  Невыделенные ячейки в этих строках или столбцах копируются в буфер обмена в виде пустых заполнителей.  
  
### Разрешение копирования ячеек  
  
-   Задайте свойство <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=fullName>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## Пример  
 В следующем полном примере кода показано, как ячейки копируются в буфер обмена.  В этом примере имеется кнопка, которая копирует выбранные ячейки в буфер обмена, используя метод <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=fullName>, и отображает содержимое буфера обмена в текстовом поле.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## Компиляция кода  
 Для этого примера кода требуются:  
  
-   ссылки на сборки N:System и N:System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Вы можете выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], вставив код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>   
 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>   
 [Выделение данных и операции с буфером обмена в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
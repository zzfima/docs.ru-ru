---
title: "Практическое руководство. Совместное использование одних и тех же данных в нескольких формах посредством компонента BindingSource | Microsoft Docs"
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
  - "BindingSource - компонент [Windows Forms], примеры"
  - "BindingSource, использование в нескольких формах"
  - "привязка данных, совместное использование данных формами"
  - "примеры [Windows Forms], BindingSource - компонент"
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Совместное использование одних и тех же данных в нескольких формах посредством компонента BindingSource
С помощью компонента <xref:System.Windows.Forms.BindingSource> одни и те же данные можно легко использовать в нескольких формах.  Например, может потребоваться отобразить одну форму только для чтения со сводкой данных и другую редактируемую форму с подробными сведениями о выбранном в данный момент элементе в источнике данных.  В этом примере демонстрируется такая возможность.  
  
## Пример  
 В примере кода ниже показано, как совместно использовать источник <xref:System.Windows.Forms.BindingSource> и связанные с ним данные в разных формах.  В этом примере общий источник <xref:System.Windows.Forms.BindingSource> передается в конструктор дочерней формы.  Дочерняя форма позволяет пользователю изменять данные элемента, выбранного в настоящий момент в главной форме.  
  
> [!NOTE]
>  В этом примере обрабатывается событие <xref:System.Windows.Forms.BindingSource.BindingComplete> для компонента <xref:System.Windows.Forms.BindingSource>, обеспечивая синхронизацию двух форм.  Подробнее о том, зачем это делать, см. в разделе [Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылки на сборки System, System.Windows.Forms, System.Drawing, System.Data и System.Xml.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Связывание элементов управления Windows Forms с данными](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Практическое руководство. Обработка ошибок и исключений, происходящих при связывании элементов управления с данными](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
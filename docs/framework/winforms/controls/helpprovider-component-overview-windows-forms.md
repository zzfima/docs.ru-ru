---
title: "Общие сведения о компоненте HelpProvider (Windows Forms) | Microsoft Docs"
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
  - "HelpProvider"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "диалоговые окна, контекстная справка"
  - "Справка F1, добавление в Windows Forms"
  - "Справка, добавление в приложения Windows"
  - "HelpProvider - компонент [Windows Forms], сведения о компоненте HelpProvider"
  - "Windows Forms, контекстная справка"
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Общие сведения о компоненте HelpProvider (Windows Forms)
Компонент форм Windows [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) используется для связи файла справки HTML Help 1.x \(файла CHM, созданного с помощью HTML Help Workshop, или файла HTM\) с приложением Windows.  Предоставить справку можно различными способами:  
  
-   предоставить контекстную справку для элементов управления Windows Forms;  
  
-   предоставить контекстную справку для определенного диалогового окна или для определенных элементов управления диалогового окна;  
  
-   открыть файл справки для определенной области, например для главной страницы оглавления, указателя или для функции поиска.  
  
## Использование элемента управления HelpProvider  
 Добавление компонента <xref:System.Windows.Forms.HelpProvider> в форму Windows Forms позволяет другим элементам управления формы предоставлять свойства Help компонента <xref:System.Windows.Forms.HelpProvider>.  Это дает возможность предоставить справку для элементов управления формы Windows Forms.  Файл справки можно связать с компонентом <xref:System.Windows.Forms.HelpProvider> с помощью свойства <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>.  Чтобы задать тип предоставляемой справки, необходимо вызвать <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> и предоставить значение перечисления <xref:System.Windows.Forms.HelpNavigator> для указанного элемента управления.  Чтобы предоставить зарезервированное слово или раздел для справки, необходимо вызвать метод <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>.  
  
 Кроме того, для связывания определенной строки справки с другим элементом управления может использоваться метод <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>.  Строка, связываемая с элементом управления при помощи этого метода, отображается во всплывающем окне, если пользователь нажимает клавишу F1, когда элемент управления находится в фокусе.  
  
 Если значение свойства <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> не задано, для предоставления текста справки необходимо использовать <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>.  Если одновременно заданы <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> и строка справки, то в первую очередь используется справка, основанная на <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>.  
  
> [!NOTE]
>  При указании относительного пути к файлу справки в методе <xref:System.Windows.Forms.Help.ShowHelp%2A> или свойстве <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> элемента управления <xref:System.Windows.Forms.HelpProvider> могут возникнуть проблемы.  По этой причине следует использовать абсолютный путь к файлу справки.  
  
## См. также  
 [Help Systems in Windows Forms Applications](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)
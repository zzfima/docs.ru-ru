---
title: "Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms. | Microsoft Docs"
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
  - "элементы управления ActiveX [Windows Forms], добавление"
  - "формы, добавление элементов управления ActiveX"
  - "элементы управления Windows Forms, элементы управления ActiveX"
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms.
Хотя конструктор Windows Forms оптимизирован для размещения элементов управления Windows Forms, в Windows Forms можно также помещать элементы управления ActiveX.  
  
> [!CAUTION]
>  Для Windows Forms существуют ограничения производительности, когда к ним добавляются элементы управления ActiveX.  
  
 Перед добавлением элементов управления ActiveX в форму необходимо добавить их в панель элементов.  Дополнительные сведения см. в разделе [Компоненты COM, диалоговое окно настройки панели элементов](http://msdn.microsoft.com/ru-ru/171333f3-f207-4e02-bbdc-17862556212c).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, выберите **Параметры импорта и экспорта** в меню **Сервис**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы добавить элемент управления ActiveX в форму Windows Forms, выполните следующие действия.  
  
-   Дважды щелкните элемент управления на панели элементов.  
  
     Все ссылки на проект будут добавлены к элементу управления с помощью [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  Дополнительные сведения о том, что нужно помнить при использовании элементов управления ActiveX в Windows Forms см. в разделе [Соображения по размещению элемента управления ActiveX в форме Windows Forms](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).  
  
    > [!NOTE]
    >  Средство импорта элементов управления ActiveX в Windows Forms — программа AxImp.exe — создает аргументы события другого типа, чем требуется при импортировании библиотек динамической компоновки ActiveX.  Аргументы, создаваемые с помощью AxImp.exe, аналогичны следующим: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, когда ожидается `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`.  Следует помнить, что подобное нарушение правил не мешает нормальной работе кода.  Подробности см. в разделе [Средство импорта элементов управления ActiveX в Windows Forms \(Aximp.exe\)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).  
  
## См. также  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Сравнение элементов управления и программируемых объектов в разных языках и библиотеках](http://msdn.microsoft.com/ru-ru/021f2a1b-8247-4348-a5ad-e1d9ab23004b)   
 [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)   
 [Расположение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Функциональная классификация элементов управления Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
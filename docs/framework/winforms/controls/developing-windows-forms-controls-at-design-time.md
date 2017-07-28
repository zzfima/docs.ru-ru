---
title: "Создание элементов управления Windows Forms во время разработки | Microsoft Docs"
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
  - "Элементы управления Windows Forms"
  - "Элементы управления Windows Forms, создание"
  - "элементы управления [Windows Forms]"
  - "Создание элементов управления [Windows Forms]"
  - "пользовательские элементы управления [Windows Forms]"
  - "пользовательские элементы управления [Windows Forms]"
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Создание элементов управления Windows Forms во время разработки
Среда .NET Framework предоставляет широкий набор технологий создания элементов управления. Авторы больше не ограничены только созданием составных элементов управления, которые действуют как коллекцию уже имеющихся элементов управления. Через наследование можно создать свои собственные элементы управления из существующих составных элементов управления или существующих элементов управления Windows Forms. Можно также создать свои собственные элементы управления, реализующие пользовательскую отрисовку. Эти возможности обеспечивают высокую степень гибкости разработки и функциональные возможности визуального интерфейса. Чтобы воспользоваться преимуществами этих функций, должны быть знакомы с понятиями объектно ориентированного программирования.  
  
> [!NOTE]
>  Это не обязательно иметь глубокие знания о наследовании, но могут оказаться полезными для обращения к [нет в построении: наследования в Visual Basic](http://msdn.microsoft.com/ru-ru/e5e6e240-ed31-4657-820c-079b7c79313c).  
  
 Если требуется создать пользовательские элементы управления для использования в Web Forms см. в разделе [Разработка пользовательских серверных элементов управления ASP.NET](../Topic/Developing%20Custom%20ASP.NET%20Server%20Controls.md).  
  
## <a name="in-this-section"></a>Содержание  
 [Пошаговое руководство: Создание составного элемента управления с помощью Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 Показан способ создания простого составного элемента управления в Visual Basic.  
  
 [Пошаговое руководство: Создание составного элемента управления с помощью Visual C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 Показывает способы создания простого составного элемента управления в C#.  
  
 [Пошаговое руководство: Наследование от элемента управления Windows Forms с помощью Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 Демонстрируется создание простого элемента управления Windows Forms с помощью наследования в Visual Basic.  
  
 [Пошаговое руководство: Наследование от элемента управления Windows Forms с помощью Visual C#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 Демонстрируется создание простого элемента управления Windows Forms с помощью наследования в C#.  
  
 [Пошаговое руководство: Выполнение типичных задач с помощью смарт-тегов в Windows Forms элементов управления](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 Показано, как использовать функцию смарт-тегов в элементах управления Windows Forms.  
  
 [Пошаговое руководство: Сериализация коллекций стандартных типов весь текст](../../../../docs/framework/winforms/controls/serializing-collections-designerserializationvisibilityattribute.md)  
 Показано, как использовать <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=fullName> атрибут для сериализации коллекции.  
  
 [Пошаговое руководство: Отладка пользовательских Windows Forms элементов управления во время разработки](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 Показан способ отладки поведения элемента управления Windows Forms во время разработки.  
  
 [Пошаговое руководство: Создание элемента управления Windows Forms, который использует преимущества средств разработки Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 Показано, как интегрировать составного элемента управления в среду разработки.  
  
 [Практическое руководство: создание элементов управления для форм Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 Общие рекомендации по реализации элемента управления Windows Forms.  
  
 [Практическое руководство: Создание составных элементов управления](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 Показано, как создать элемент управления путем наследования из составного элемента управления.  
  
 [Практическое руководство: наследование класса UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 Обзор процедуры для создания составного элемента управления.  
  
 [Практическое руководство: наследование существующих Windows Forms-элементы управления](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 Описание способов создания расширенного элемента управления путем наследования от <xref:System.Windows.Forms.Button> класса элемента управления.  
  
 [Практическое руководство: наследуют от класса Control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 Обзор создания расширенного элемента управления.  
  
 [Практическое руководство: выравнивание элементов управления по границам формы во время разработки](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 Показано, как использовать <xref:System.Windows.Forms.Control.Dock%2A> свойство для выравнивания пользовательского элемента управления по краю занимаемой им формы.  
  
 [Практическое руководство: отображение элемента управления в Выбор элементов панели элементов-диалоговое окно](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 Описание процедуры установки собственного элемента управления, чтобы он отображался в **Настройка инструментария** диалоговое окно.  
  
 [Практическое руководство: предоставление точечного рисунка панели элементов для элемента управления](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 Показано, как использовать <xref:System.Drawing.ToolboxBitmapAttribute> для отображения значка рядом с пользовательского элемента управления в **элементов**.  
  
 [Практическое руководство: Проверьте поведение пользовательского элемента управления](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 Показано, как использовать **тестового контейнера пользовательских элементов управления** для тестирования поведения составного элемента управления.  
  
 [Ошибки во время разработки в конструкторе Windows Forms](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 Объясняет значение и использование списка ошибок во время разработки, отображаемого в Microsoft Visual Studio при невозможности загрузить конструктор Windows Forms.  
  
 [Устранение неполадок управления и создания компонентов](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 Показано, как определять и исправлять распространенные проблемы, возникающие при разработке пользовательского компонента или элемента управления.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.Control?displayProperty=fullName>  
 Описывает данный класс и предоставляет ссылки на все его члены.  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>  
 Описывает данный класс и предоставляет ссылки на все его члены.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Разработка пользовательских Windows Forms элементов управления .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 Описывается создание пользовательских элементов управления с помощью .NET Framework.  
  
 [Независимость от языка и независимые от языка компоненты](../../../../docs/standard/language-independence-and-language-independent-components.md)  
 Представляет общеязыковой средой выполнения, которая предназначена для упрощения создания и использования компонентов. Важным аспектом этого упрощения является расширение возможностей взаимодействия между компонентами, написанными на разных языках программирования. Язык спецификации (CLS) делает возможным создание инструментов и компонентов, которые работают с несколькими языками программирования.  
  
 [Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 Описывает способ включения компонентов или элементов управления для отображения в **Настройка инструментария** диалоговое окно.
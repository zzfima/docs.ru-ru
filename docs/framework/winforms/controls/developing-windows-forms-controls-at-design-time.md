---
title: Создание элементов управления Windows Forms во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
ms.openlocfilehash: 267a56cbfd9025e2e20f1468535e5544146535a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="developing-windows-forms-controls-at-design-time"></a>Создание элементов управления Windows Forms во время разработки
Среда .NET Framework предоставляет широкий набор технологий создания элементов управления. Авторы больше не ограничены созданием составных элементов управления, которые действуют как коллекция стандартных элементов управления. Через наследование можно создать свои собственные элементы управления на основе существующих составных элементов управления или существующих элементов управления Windows Forms. Можно также создать собственные элементы управления, реализующие настраиваемое рисование. Эти возможности обеспечивают высокую степень гибкости разработки и функциональности визуального интерфейса. Чтобы воспользоваться преимуществами этих функций, вы должны быть знакомы с понятиями объектно-ориентированного программирования.  
  
> [!NOTE]
>  Это не обязательно иметь глубокие знания о наследовании, но могут оказаться полезными для обращения к [Основы наследования (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Если вам необходимо создать пользовательский элемент управления для использования в веб-формах, см. раздел [Разработка пользовательских серверных элементов управления ASP.NET](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Пошаговое руководство. Создание составного элемента управления с помощью Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 Демонстрируется создание простого составного элемента управления в Visual Basic.  
  
 [Пример. Создание составного элемента управления с помощью C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 Демонстрируется создание простого составного элемента управления в C#.  
  
 [Пошаговое руководство. Наследование элементов управления форм Windows Forms с помощью Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 Демонстрируется создание простого элемента управления Windows Forms с помощью наследования в Visual Basic.  
  
 [Пошаговое руководство. Наследование элементов управления форм Windows Forms с помощью Visual C#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 Демонстрируется создание простого элемента управления Windows Forms с помощью наследования в C#.  
  
 [Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 Демонстрируется использование функции смарт-тегов в элементах управления Windows Forms.  
  
 [Пошаговое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute](../../../../docs/framework/winforms/controls/serializing-collections-designerserializationvisibilityattribute.md)  
 Показано, как использовать <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> атрибут для сериализации коллекции.  
  
 [Пошаговое руководство. Отладка пользовательских элементов управления Windows Forms во время разработки](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 Демонстрируется процедура отладки поведения элемента управления Windows Forms во время разработки.  
  
 [Пошаговое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций Visual Studio, применяемых во время разработки](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 Демонстрируется интеграция составного элемента управления в среду разработки.  
  
 [Практическое руководство. Создание элементов управления для форм Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 Общие рекомендации по реализации элемента управления Windows Forms.  
  
 [Практическое руководство. Создание составных элементов управления](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 Демонстрируется создание элемента управления путем наследования из составного элемента управления.  
  
 [Практическое руководство. Наследование класса UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 Обзор процедуры создания составного элемента управления.  
  
 [Практическое руководство. Наследование существующих элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 Описание способов создания расширенного элемента управления путем наследования от <xref:System.Windows.Forms.Button> класса элемента управления.  
  
 [Практическое руководство. Наследование класса Control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 Обзор создания расширенного элемента управления.  
  
 [Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 Показано, как использовать <xref:System.Windows.Forms.Control.Dock%2A> свойства для выравнивания пользовательского элемента управления по краю занимаемой им формы.  
  
 [Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 Описание процедуры установки элемента управления таким образом, чтобы он отображался в диалоговом окне **Настройка области элементов**.  
  
 [Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 Показано, как использовать <xref:System.Drawing.ToolboxBitmapAttribute> для отображения значка рядом с пользовательского элемента управления в **элементов**.  
  
 [Практическое руководство. Тестирование поведения элемента UserControl во время выполнения](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 Демонстрируется использование **тестового контейнера UserControl** для тестирования поведения составного элемента управления.  
  
 [Ошибки во время разработки в конструкторе Windows Forms](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 Объяснение значения и использования списка ошибок во время разработки, отображаемого в Microsoft Visual Studio при невозможности загрузить конструктор Windows Forms.  
  
 [Разрешение вопросов, связанных с созданием элементов управления и компонентов](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 Демонстрируются диагностика и исправление распространенных проблем, возникающих при разработке пользовательского компонента или элемента управления.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 Описывает данный класс и предоставляет ссылки на все его члены.  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 Описывает данный класс и предоставляет ссылки на все его члены.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Разработка пользовательских элементов управления Windows Forms в .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 Описывается создание пользовательских элементов управления с помощью .NET Framework.  
  
 [Независимость от языка и независимые от языка компоненты](../../../../docs/standard/language-independence-and-language-independent-components.md)  
 Основные сведения об общеязыковой среде выполнения (CLR), которая предназначена для упрощения создания и использования компонентов. Важным аспектом этого упрощения является расширение возможностей взаимодействия между компонентами, написанными на разных языках программирования. Спецификация CLS делает возможным создание инструментов и компонентов, которые работают с несколькими языками программирования.  
  
 [Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 Описание включения компонентов или элементов управления для отображения в диалоговом окне **Настройка области элементов**.

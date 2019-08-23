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
ms.openlocfilehash: 11c3d9d6e7faa4741365316339d38f9fda69d059
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965710"
---
# <a name="developing-windows-forms-controls-at-design-time"></a>Создание элементов управления Windows Forms во время разработки
Среда .NET Framework предоставляет широкий набор технологий создания элементов управления. Авторы больше не ограничены созданием составных элементов управления, которые действуют как коллекция стандартных элементов управления. Через наследование можно создать свои собственные элементы управления на основе существующих составных элементов управления или существующих элементов управления Windows Forms. Можно также создать собственные элементы управления, реализующие настраиваемое рисование. Эти возможности обеспечивают высокую степень гибкости разработки и функциональности визуального интерфейса. Чтобы воспользоваться преимуществами этих функций, вы должны быть знакомы с понятиями объектно-ориентированного программирования.  
  
> [!NOTE]
> Нет необходимости глубокого понимания наследования, но может оказаться полезным ознакомиться с [основами наследования (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Если вам необходимо создать пользовательский элемент управления для использования в веб-формах, см. раздел [Разработка пользовательских серверных элементов управления ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Пошаговое руководство: Создание составного элемента управления с помощью Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 Демонстрируется создание простого составного элемента управления в Visual Basic.  
  
 [Пошаговое руководство: Создание составного элемента управления с помощью VisualC#](walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 Демонстрируется создание простого составного элемента управления в C#.  
  
 [Пошаговое руководство: Наследование от элемента управления Windows Forms с помощью Visual Basic](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 Демонстрируется создание простого элемента управления Windows Forms с помощью наследования в Visual Basic.  
  
 [Пошаговое руководство: Наследование от элемента управления Windows Forms с помощью VisualC#](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 Демонстрируется создание простого элемента управления Windows Forms с помощью наследования в C#.  
  
 [Пошаговое руководство: Выполнение стандартных задач с помощью смарт-тегов в элементах управления Windows Forms](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 Демонстрируется использование функции смарт-тегов в элементах управления Windows Forms.  
  
 [Пошаговое руководство: Сериализация коллекций стандартных типов с помощью Десигнерсериализатионвисибилитяттрибуте](serializing-collections-designerserializationvisibilityattribute.md)  
 Показывает, как использовать <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> атрибут для сериализации коллекции.  
  
 [Пошаговое руководство: Отладка пользовательских элементов управления Windows Forms во время разработки](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 Демонстрируется процедура отладки поведения элемента управления Windows Forms во время разработки.  
  
 [Пошаговое руководство: Создание элемента управления Windows Forms, который использует преимущества функций времени разработки Visual Studio](creating-a-wf-control-design-time-features.md)  
 Демонстрируется интеграция составного элемента управления в среду разработки.  
  
 [Практическое руководство. Создание элементов управления для Windows Forms](how-to-author-controls-for-windows-forms.md)  
 Общие рекомендации по реализации элемента управления Windows Forms.  
  
 [Практическое руководство. Создание составных элементов управления](how-to-author-composite-controls.md)  
 Демонстрируется создание элемента управления путем наследования из составного элемента управления.  
  
 [Практическое руководство. Наследование от класса UserControl](how-to-inherit-from-the-usercontrol-class.md)  
 Обзор процедуры создания составного элемента управления.  
  
 [Практическое руководство. Наследовать от существующих элементов управления Windows Forms](how-to-inherit-from-existing-windows-forms-controls.md)  
 Демонстрирует создание расширенного элемента управления путем наследования от <xref:System.Windows.Forms.Button> класса Control.  
  
 [Практическое руководство. Наследование от класса Control](how-to-inherit-from-the-control-class.md)  
 Обзор создания расширенного элемента управления.  
  
 [Практическое руководство. Выровняйте элемент управления по краям форм во время разработки](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 Показывает, как использовать <xref:System.Windows.Forms.Control.Dock%2A> свойство для согласования элемента управления с границей занимаемой им формы.  
  
 [Практическое руководство. Отображение элемента управления в диалоговом окне "Выбор элементов панели элементов"](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 Описание процедуры установки элемента управления таким образом, чтобы он отображался в диалоговом окне **Настройка области элементов**.  
  
 [Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления](how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 Показывает, как использовать <xref:System.Drawing.ToolboxBitmapAttribute> для отображения значка рядом с пользовательским элементом управления на **панели элементов**.  
  
 [Практическое руководство. Проверка поведения элемента управления UserControl во время выполнения](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 Демонстрируется использование **тестового контейнера UserControl** для тестирования поведения составного элемента управления.  
  
 [Ошибки во время разработки в конструкторе Windows Forms](design-time-errors-in-the-windows-forms-designer.md)  
 Объяснение значения и использования списка ошибок во время разработки, отображаемого в Microsoft Visual Studio при невозможности загрузить конструктор Windows Forms.  
  
 [Разрешение вопросов, связанных с созданием элементов управления и компонентов](troubleshooting-control-and-component-authoring.md)  
 Демонстрируются диагностика и исправление распространенных проблем, возникающих при разработке пользовательского компонента или элемента управления.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 Описывает данный класс и предоставляет ссылки на все его члены.  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 Описывает данный класс и предоставляет ссылки на все его члены.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Разработка пользовательских элементов управления Windows Forms в .NET Framework](developing-custom-windows-forms-controls.md)  
 Описывается создание пользовательских элементов управления с помощью .NET Framework.  
  
 [Независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md)  
 Основные сведения об общеязыковой среде выполнения (CLR), которая предназначена для упрощения создания и использования компонентов. Важным аспектом этого упрощения является расширение возможностей взаимодействия между компонентами, написанными на разных языках программирования. Спецификация CLS делает возможным создание инструментов и компонентов, которые работают с несколькими языками программирования.  
  
 [Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 Описание включения компонентов или элементов управления для отображения в диалоговом окне **Настройка области элементов**.

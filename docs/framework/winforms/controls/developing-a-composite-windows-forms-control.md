---
title: Разработка составного элемента Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: 24fbf17f02072b2d9922ca0998805b916afc41b6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463713"
---
# <a name="developing-a-composite-windows-forms-control"></a>Разработка составного элемента Windows Forms
Можно разработать составной элемент управления Windows Forms, объединив другие элементы управления Windows Forms. Составные элементы управления, которые являются производными от <xref:System.Web.UI.UserControl> называются пользовательскими элементами управления. Базовый класс <xref:System.Windows.Forms.UserControl> обеспечивает маршрутизацию событий клавиатуры для дочерних элементов управления, это гарантирует, что дочерние элементы управления смогут получать фокус ввода. Пример пользовательского элемента управления, см. в разделе <xref:System.Windows.Forms.UserControl> в [как: применение атрибутов в элементах управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).  
  
 Конструктор Windows Forms в [!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)] предоставляет широкие возможности поддержки для пользовательских элементов управления во время разработки.  
  
-   [Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов](https://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))  
  
-   [Пошаговое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)  
  
-   [Пример. Наследование элементов управления форм Windows Forms с помощью Visual C#](https://msdn.microsoft.com/library/09476da0-8d4c-4a4c-b969-649519dfb438)  
  
-   [Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления](https://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))  
  
-   [Практическое руководство. Наследование существующих элементов управления Windows Forms](https://msdn.microsoft.com/library/7h62478z\(v=vs.110\))  
  
-   [Пошаговое руководство. Отладка пользовательских элементов управления Windows Forms во время разработки](https://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))  
  
-   [Практическое руководство. Наследование класса Control](https://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))  
  
-   [Практическое руководство. Тестирование поведения элемента UserControl во время выполнения](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
  
-   [Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения](https://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))  
  
-   [Практическое руководство. Наследование класса UserControl](https://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))  
  
-   [Практическое руководство. Создание элементов управления для форм Windows Forms](https://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))  
  
-   [Практическое руководство. Создание составных элементов управления](https://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))  
  
-   [Пошаговое руководство. Создание составного элемента управления с помощью Visual Basic](https://msdn.microsoft.com/library/c316f119\(v=vs.110\))  
  
-   [Пример. Создание составного элемента управления с помощью C#](https://msdn.microsoft.com/library/f88481a8-c746-4a36-9479-374ce5f2e91f)  
  
-   [Пошаговое руководство. Наследование элементов управления форм Windows Forms с помощью Visual Basic](https://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))  
  
-   [Практическое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций, применяемых во время разработки](https://msdn.microsoft.com/library/307hck25\(v=vs.110\))  
  
-   [Практическое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций, применяемых во время разработки](https://msdn.microsoft.com/library/307hck25\(v=vs.120\))  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Применение атрибутов к элементам управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)  
 [Разработка пользовательских элементов управления Windows Forms в .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Разновидности пользовательских элементов управления](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)

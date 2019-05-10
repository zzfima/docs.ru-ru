---
title: Практическое руководство. Тестирование поведения элемента UserControl во время выполнения
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 48531ab1ef3b30b6516e3f2e7b5858a8884cbfe8
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211710"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Практическое руководство. Тестирование во время выполнения поведения элемента UserControl

При разработке <xref:System.Windows.Forms.UserControl>, необходимо проверить его поведение во время выполнения. Можно создать проект отдельные приложения на основе Windows и разместить элемент управления в тестовую форму, но эта процедура неудобно. Быстрый и удобный способ — использовать **тестовом контейнере элементов управления** , предоставляемые Visual Studio. Тестовый контейнер запускается непосредственно из проект библиотеки элементов управления Windows.

> [!IMPORTANT]
> К контейнеру теста для загрузки вашего <xref:System.Windows.Forms.UserControl>, элемент управления должен иметь по крайней мере один открытый конструктор.

> [!NOTE]
> Элемент управления Visual C++ не может быть проверен с использованием **тестовом контейнере элементов управления**.

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a>Тестирование во время выполнения поведения элемента UserControl

1. В Visual Studio создайте проект библиотеки элементов управления Windows вызывается **TestContainerExample**. Дополнительные сведения см. в разделе [шаблон библиотеки элементов управления Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).

2. В **конструктор Windows Forms**, перетащите <xref:System.Windows.Forms.Label> управления из **элементов** в область конструктора элемента управления.

3. Нажмите клавишу **F5** для сборки проекта и запуска **тестовом контейнере элементов управления**. Тестовый контейнер будет отображаться с вашей <xref:System.Windows.Forms.UserControl> в **предварительной версии** области.

4. Выберите <xref:System.Windows.Forms.Control.BackColor%2A> свойство, отображаемое в <xref:System.Windows.Forms.PropertyGrid> управления справа от **предварительной версии** области. Измените его значение на `ControlDark`. Обратите внимание, что элемент управления примет более темным цветом. Попробуйте изменить значения других свойств и понаблюдайте за влияние на элемент управления.

5. Нажмите кнопку **окно** флажок ниже **предварительной версии** области. Обратите внимание, что элемент управления изменяется для заполнения области. Измените размер тестового контейнера и обратите внимание, что элемент управления при изменении размеров области.

6. Закройте тестовый контейнер.

7. Добавить другой пользовательский элемент управления для **TestContainerExample** проекта. Подробную информацию см. в разделе [Практическое руководство. Добавление существующих элементов в проект](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).

8. В **конструктор Windows Forms**, перетащите <xref:System.Windows.Forms.Button> управления из **элементов** в область конструктора элемента управления.

9. Нажмите клавишу F5 для сборки проекта и запуска тестового контейнера.

10. Нажмите кнопку **выберите пользовательский элемент управления** <xref:System.Windows.Forms.ComboBox> для переключения между двумя элементами управления.

## <a name="test-user-controls-from-another-project"></a>Проверка пользовательских элементов управления из другого проекта

Пользовательские элементы управления из других проектов можно проверить в тестовом контейнере текущего проекта.

1. Создайте проект библиотеки элементов управления Windows вызывается **TestContainerExample2**. Дополнительные сведения см. в разделе [шаблон библиотеки элементов управления Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).

2. В **конструктор Windows Forms**, перетащите <xref:System.Windows.Forms.RadioButton> управления из **элементов** в область конструктора элемента управления.

3. Нажмите клавишу F5 для сборки проекта и запуска тестового контейнера. Тестовый контейнер будет отображаться с вашей <xref:System.Windows.Forms.UserControl> в **предварительной версии** области.

4. Нажмите кнопку **нагрузки** кнопки.

5. В **откройте** диалоговом окне перейдите к **TestContainerExample**.dll, который встроен в предыдущей процедуре. Выберите **TestContainerExample**DLL-файл и нажмите кнопку **откройте** кнопку, чтобы загрузить пользовательские элементы управления

6. Используйте **выберите пользовательский элемент управления** <xref:System.Windows.Forms.ComboBox> для переключения между двумя элементами управления из **TestContainerExample** проекта.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.UserControl>
- [Практическое руководство. Создание составных элементов управления](how-to-author-composite-controls.md)
- [Пошаговое руководство: Создание составного элемента управления с помощью Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [Пошаговое руководство: Создание составного элемента управления с помощью VisualC#](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [Конструктор пользовательских элементов управления](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))

---
title: Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 1cc854d735ba88a301d6e2f6a83fe5c8bf881380
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211421"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a>Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms

При создании форм и элементов управления для приложения Windows Forms есть множество задач, которые выполняются несколько раз. Ниже перечислены некоторые наиболее типичных задач, которыми вы столкнетесь:

- Добавление или удаление вкладки в <xref:System.Windows.Forms.TabControl>.

- Закрепление элемента управления своему родителю.

- Изменение ориентации элемента <xref:System.Windows.Forms.SplitContainer> элемента управления.

Для ускорения разработки, многие элементы управления обеспечивают смарт-тегов, которые являются контекстные меню, позволяющие выполнять общие задачи, как они в одном жесте во время разработки. Эти задачи называются *командами смарт тегов*.

Смарт-теги остаются прикрепленными к экземпляра элемента управления для существования в конструкторе и всегда доступны.

В данном пошаговом руководстве представлены следующие задачи.

- Создание проекта Windows Forms

- С помощью смарт-тегов

- Включение и отключение смарт-тегов

После завершения вы будете понимать роль, которую играют эти важные функции макета.

## <a name="create-the-project"></a>Создание проекта

Первым шагом является создание проекта и настройка формы.

1. В Visual Studio создайте проект приложения на основе Windows с именем «SmartTagsExample» (**файл** > **New** > **проекта**  >  **Visual C#**  или **Visual Basic** > **классический рабочий стол** > **Windows Forms Приложение**).

2. Выберите форму в **конструктор Windows Forms**.

## <a name="use-smart-tags"></a>С помощью смарт-тегов

Смарт-тегов постоянную доступность во время разработки для элементов управления, которые содержат их.

1. Перетащите <xref:System.Windows.Forms.TabControl> из **элементов** на форму. Обратите внимание, глиф смарт тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), отображаемый на краю <xref:System.Windows.Forms.TabControl>.

2. Щелкните глиф смарт тега. Выберите в контекстном меню, отображаемый рядом с глифом, **добавить вкладку** элемента. Обратите внимание, что новую страницу вкладки добавляется <xref:System.Windows.Forms.TabControl>.

3. Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.

4. Щелкните глиф смарт тега. Выберите в контекстном меню, отображаемый рядом с глифом, **добавить столбец** элемента. Обратите внимание, что новый столбец будет добавлен <xref:System.Windows.Forms.TableLayoutPanel> элемента управления.

5. Перетащите элемент управления <xref:System.Windows.Forms.SplitContainer> из **панели элементов** в свою форму.

6. Щелкните глиф смарт тега. Выберите в контекстном меню, отображаемый рядом с глифом, **Ориентация горизонтального разделителя** элемента. Обратите внимание, что <xref:System.Windows.Forms.SplitContainer> разделителя элемента управления — теперь горизонтальную ориентацию.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- [Пошаговое руководство: Добавление смарт-тегов в компонент Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))

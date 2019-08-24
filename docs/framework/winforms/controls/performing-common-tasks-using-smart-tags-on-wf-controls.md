---
title: Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 34c14c0afd9632b06947fd72e46ddbda070cfb0f
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015761"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a>Пошаговое руководство. Выполнение стандартных задач с помощью смарт-тегов

При создании форм и элементов управления для приложения Windows Forms существует множество задач, которые будут выполняться многократно. Ниже приведены некоторые из типичных выполняемых задач.

- Добавление или удаление вкладки в <xref:System.Windows.Forms.TabControl>.

- Закрепление элемента управления в его родительском элементе.

- Изменение ориентации <xref:System.Windows.Forms.SplitContainer> элемента управления.

Для ускорения разработки многие элементы управления предлагают интеллектуальные теги, которые представляют собой контекстно-зависимые меню, позволяющие выполнять общие задачи, такие как, в одном жесте во время разработки. Эти задачи называются *командами смарт-тегов*.

Смарт-теги остаются присоединенными к экземпляру элемента управления на время его существования в конструкторе и всегда доступны.

## <a name="create-the-project"></a>Создание проекта

Первым шагом является создание проекта и настройка формы.

1. В Visual Studio создайте проект приложения на основе Windows с именем **смарттагсексампле**.

2. Выберите форму в **конструктор Windows Forms**.

## <a name="use-smart-tags"></a>Использование смарт-тегов

Смарт-теги всегда доступны во время разработки в элементах управления, которые их предлагают.

1. Перетащите элемент <xref:System.Windows.Forms.TabControl> из **области элементов** на форму. Обратите внимание на глиф![](./media/vs-winformsmttagglyph.gif)смарт-тега, который отображается <xref:System.Windows.Forms.TabControl>на стороне.

2. Щелкните глиф смарт-тега. В контекстном меню, расположенном рядом с глифом, выберите элемент **вкладка добавить** . Обратите внимание, что новая страница вкладки добавляется <xref:System.Windows.Forms.TabControl>в.

3. Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.

4. Щелкните глиф смарт-тега. В контекстном меню рядом с глифом выберите элемент **Добавить столбец** . Обратите внимание, что к <xref:System.Windows.Forms.TableLayoutPanel> элементу управления добавляется новый столбец.

5. Перетащите элемент управления <xref:System.Windows.Forms.SplitContainer> из **панели элементов** в свою форму.

6. Щелкните глиф смарт-тега. В контекстном меню, расположенном рядом с глифом, выберите элемент **ориентация разделителя по горизонтали** . Обратите внимание <xref:System.Windows.Forms.SplitContainer> , что теперь полоса разделения элемента управления ориентирована горизонтально.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>

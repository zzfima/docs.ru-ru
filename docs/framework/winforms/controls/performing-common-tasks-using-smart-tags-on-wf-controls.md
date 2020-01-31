---
title: Перформи общие задачи с помощью смарт-тегов в элементах управления
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 826313d0a89410f62c034a5fba4dee32e90a1750
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744258"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a>Пошаговое руководство. выполнение стандартных задач с помощью смарт-тегов

При создании форм и элементов управления для приложения Windows Forms существует множество задач, которые будут выполняться многократно. Ниже приведены некоторые из типичных выполняемых задач.

- Добавление или удаление вкладки <xref:System.Windows.Forms.TabControl>.

- Закрепление элемента управления в его родительском элементе.

- Изменение ориентации элемента управления <xref:System.Windows.Forms.SplitContainer>.

Для ускорения разработки многие элементы управления предлагают интеллектуальные теги, которые представляют собой контекстно-зависимые меню, позволяющие выполнять общие задачи, такие как, в одном жесте во время разработки. Эти задачи называются *командами смарт-тегов*.

Смарт-теги остаются присоединенными к экземпляру элемента управления на время его существования в конструкторе и всегда доступны.

## <a name="create-the-project"></a>Создание проекта

Первым шагом является создание проекта и настройка формы.

1. В Visual Studio создайте проект приложения на основе Windows с именем **смарттагсексампле**.

2. Выберите форму в **конструктор Windows Forms**.

## <a name="use-smart-tags"></a>Использование смарт-тегов

Смарт-теги всегда доступны во время разработки в элементах управления, которые их предлагают.

1. Перетащите <xref:System.Windows.Forms.TabControl> с **панели элементов** на форму. Обратите внимание, что глиф смарт-тега (![](./media/vs-winformsmttagglyph.gif)глифов, отображается на стороне <xref:System.Windows.Forms.TabControl>.

2. Щелкните глиф смарт-тега. В контекстном меню, расположенном рядом с глифом, выберите элемент **вкладка добавить** . Обратите внимание, что новая страница вкладки добавляется в <xref:System.Windows.Forms.TabControl>.

3. Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.

4. Щелкните глиф смарт-тега. В контекстном меню рядом с глифом выберите элемент **Добавить столбец** . Обратите внимание, что новый столбец добавляется к элементу управления <xref:System.Windows.Forms.TableLayoutPanel>.

5. Перетащите элемент управления <xref:System.Windows.Forms.SplitContainer> из **панели элементов** в свою форму.

6. Щелкните глиф смарт-тега. В контекстном меню, расположенном рядом с глифом, выберите элемент **ориентация разделителя по горизонтали** . Обратите внимание, что теперь Панель разделителя элемента управления <xref:System.Windows.Forms.SplitContainer> ориентирована горизонтально.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>

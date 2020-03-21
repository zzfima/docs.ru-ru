---
title: Отладка деревьев выражений в Visual Studio
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: c6c44d079ab0854b2325b82d3569280752da32fb
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266837"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Отладка деревьев выражения в визуальной студии (Visual Basic)
При отладке приложений можно анализировать структуру и содержимое деревьев выражений. Чтобы получить краткий обзор структуры дерева выражения, вы можете использовать свойство `DebugView`, которое представляет деревья выражений, [используя специальный синтаксис](debugview-syntax.md). (Обратите внимание, что `DebugView` доступен только в режиме отладки.)  

![Скриншот дерева выражения DebugView.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

Так как `DebugView` представляет собой строку, можно использовать [встроенный визуализатор текста](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) для его просмотра по нескольким строкам, выбрав **визуализатор текста** из меню со значком лупы рядом с меткой `DebugView`.

 ![Скриншот text Visualizer применяется к результатам DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

Или вы можете установить и использовать [пользовательский визуализатор](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) для деревьев выражений, например:

- [Выражения для чтения](https://github.com/agileobjects/ReadableExpressions) ([лицензия MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), доступная в [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), отображают дерево выражения в виде кода C#:

  ![Снимок экрана: визуализатор доступных для чтения выражений](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- [Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) [(лицензия MIT),](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)обеспечивает графическое представление дерева выражения, его свойств и связанных с ними объектов; и может визуализировать дерево выражения с помощью визуального базового кода:

  ![Скриншот визуализатора ExpressionToString.](media/debugging-expression-trees-in-visual-studio/expression-to-string-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Открытие визуализатора дерева выражения  
  
1. Щелкните значок лупы рядом с деревом выражения в окне **Подсказки по данным**, **Контрольные значения**, **Видимые** или **Локальные**.  
  
    Отображается список доступных визуализаторов:

    ![Скриншот открывающихся визуализаторов пользователя от Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. Щелкните визуализатор, который необходимо использовать.  

## <a name="see-also"></a>См. также раздел

- [Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))
- [Отладка в Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Создание настраиваемых визуализаторов](/visualstudio/debugger/create-custom-visualizers-of-data)
- [Синтаксис `DebugView`](debugview-syntax.md)

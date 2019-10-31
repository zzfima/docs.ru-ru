---
title: Отладка деревьев выражений в Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: b27ab41f3c3d9bd488fd0f7aaa5010f2997946de
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198270"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Отладка деревьев выражений в Visual Studio (Visual Basic)
При отладке приложений можно анализировать структуру и содержимое деревьев выражений. Чтобы получить краткий обзор структуры дерева выражения, вы можете использовать свойство `DebugView`, которое представляет деревья выражений, [используя специальный синтаксис](debugview-syntax.md). (Обратите внимание, что `DebugView` доступен только в режиме отладки.)  

![Снимок экрана DebugView дерева выражения.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

Так как `DebugView` представляет собой строку, можно использовать [встроенный визуализатор текста](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) для его просмотра по нескольким строкам, выбрав **визуализатор текста** из меню со значком лупы рядом с меткой `DebugView`.

 ![Снимок экрана: визуализатор текста, примененный к результатам DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

Или вы можете установить и использовать [пользовательский визуализатор](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) для деревьев выражений, например:

- [Выражения для чтения](https://github.com/agileobjects/ReadableExpressions) ([лицензия MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), доступная в [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), отображают дерево выражения в виде кода C#:

  ![Снимок экрана: визуализатор доступных для чтения выражений](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- [Визуализатор дерева выражений](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([Лицензия MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)) предоставляет графическое представление дерева выражений, его свойств и связанных объектов. и могут визуализировать дерево выражения с помощью Visual Basic кода:

  ![Снимок экрана визуализатора Експрессионтостринг.](media/debugging-expression-trees-in-visual-studio/expression-to-string-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Открытие визуализатора дерева выражения  
  
1. Щелкните значок лупы рядом с деревом выражения в окне **Подсказки по данным**, **Контрольные значения**, **Видимые** или **Локальные**.  
  
    Отображается список доступных визуализаторов: 

    ![Снимок экрана пользователя, открывающего визуализаторы из Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. Щелкните визуализатор, который необходимо использовать.  

## <a name="see-also"></a>См. также

- [Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))
- [Отладка в Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Создание настраиваемых визуализаторов](/visualstudio/debugger/create-custom-visualizers-of-data)
- [Синтаксис `DebugView`](debugview-syntax.md)

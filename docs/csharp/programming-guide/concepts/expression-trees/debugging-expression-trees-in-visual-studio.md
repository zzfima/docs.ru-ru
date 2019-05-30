---
title: Отладка деревьев выражений в Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 93b1b660181cd81c31055f5d30d43e535171bb55
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2019
ms.locfileid: "66195987"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a>Отладка деревьев выражений в Visual Studio (C#)
При отладке приложений можно анализировать структуру и содержимое деревьев выражений. Чтобы получить краткий обзор структуры дерева выражения, вы можете использовать свойство `DebugView`, которое представляет деревья выражений, [используя специальный синтаксис](debugview-syntax.md). (Обратите внимание, что `DebugView` доступен только в режиме отладки.)  

![DebugView дерева выражения в отладчике Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview.png)

Так как `DebugView` представляет собой строку, можно использовать [встроенный визуализатор текста](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) для его просмотра по нескольким строкам, выбрав **визуализатор текста** из меню со значком лупы рядом с меткой `DebugView`.

 ![Визуализатор текста применяется к результатам DebugView](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

Или вы можете установить и использовать [пользовательский визуализатор](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) для деревьев выражений, например:

* [Выражения для чтения](https://github.com/agileobjects/ReadableExpressions) ([лицензия MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), доступная в [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), отображают дерево выражения в виде кода C#:

  ![Визуализатор выражений для чтения](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* [Визуализатор дерева выражения](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([лицензия MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)) предоставляет графическое представление дерева выражения, его свойства и связанные объекты:

  ![Визуализатор ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Открытие визуализатора дерева выражения  
  
1. Щелкните значок лупы рядом с деревом выражения в окне **Подсказки по данным**, **Контрольные значения**, **Видимые** или **Локальные**.  
  
     Отображается список доступных визуализаторов: 

      ![Открытие визуализаторов из Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. Щелкните визуализатор, который необходимо использовать.  
  
## <a name="see-also"></a>См. также

- [Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (C#))
- [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)
- [Создание настраиваемых визуализаторов](/visualstudio/debugger/create-custom-visualizers-of-data)
- [Синтаксис `DebugView`](debugview-syntax.md)

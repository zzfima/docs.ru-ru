---
title: Оператор GetType (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 34ab192814583db5cdc0d0183c73cc22b8633e9c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840326"
---
# <a name="gettype-operator-visual-basic"></a>Оператор GetType (Visual Basic)
Возвращает <xref:System.Type> объекта для указанного типа. <xref:System.Type> Объект предоставляет сведения о типе, например его свойства, методы и события.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
GetType(typename)  
```  
  
## <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---|---|  
|`typename`|Имя типа, для которого необходимы сведения.|  
  
## <a name="remarks"></a>Примечания  
 `GetType` Оператор возвращает <xref:System.Type> для указанного `typename`. Можно передать имя любого типа в `typename`. Это поведение характеризуется следующим образом.  
  
-   Любой Visual Basic тип данных, таких как `Boolean` или `Date`.  
  
-   Любой платформы .NET Framework класс, структура, модуль или интерфейс, такие как <xref:System.ArgumentException?displayProperty=nameWithType> или <xref:System.Double?displayProperty=nameWithType>.  
  
-   Любой класс, структура, модуль или интерфейс, определяемый приложением.  
  
-   Любой массив, определяемый приложением.  
  
-   Любому делегату, заданных вашим приложением.  
  
-   Любое перечисление, определенное в Visual Basic, .NET Framework или приложения.  
  
 Если вы хотите получить объект типа переменной объекта, используйте <xref:System.Type.GetType%2A?displayProperty=nameWithType> метод.  
  
 `GetType` Оператор может быть полезно в следующих случаях:  
  
-   Доступ к метаданным для типа необходимо во время выполнения. <xref:System.Type> Предоставляет метаданные, такие как члены типа и сведения о развертывании. Это необходимо, например, чтобы отобразить сборку. Дополнительные сведения см. в разделе <xref:System.Reflection?displayProperty=nameWithType>.  
  
-   Вы хотите сравнить две объектные ссылки, чтобы увидеть, если они относятся к экземплярам того же типа. Если это так, `GetType` возвращает ссылки на один и тот же <xref:System.Type> объекта.  
  
## <a name="example"></a>Пример  
 В приведенных ниже примерах `GetType` оператор используется.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>См. также

- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)

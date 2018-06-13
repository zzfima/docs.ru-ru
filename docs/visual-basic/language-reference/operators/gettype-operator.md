---
title: Оператор GetType (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 581f576222eb149aede841a5da7a0e5f38c77b58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603851"
---
# <a name="gettype-operator-visual-basic"></a>Оператор GetType (Visual Basic)
Возвращает <xref:System.Type> объекта для указанного типа. <xref:System.Type> Объект предоставляет сведения о типе, например его свойства, методы и события.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
GetType(typename)  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---|---|  
|`typename`|Имя типа, для которого требуется получить сведения.|  
  
## <a name="remarks"></a>Примечания  
 `GetType` Оператор возвращает <xref:System.Type> для указанного `typename`. Можно передать имя любого типа в `typename`. Это поведение характеризуется следующим образом.  
  
-   Тип данных Visual Basic, например `Boolean` или `Date`.  
  
-   Все платформы .NET Framework класса, структуры, модуля или интерфейса, такие как <xref:System.ArgumentException?displayProperty=nameWithType> или <xref:System.Double?displayProperty=nameWithType>.  
  
-   Любой класс, структура, модуль или интерфейс, определяемый приложением.  
  
-   Любой массив, определяемый приложением.  
  
-   Любой делегат, определяемый приложением.  
  
-   Любое перечисление, определенное в Visual Basic .NET Framework и приложения.  
  
 Если вы хотите получить объект типа переменной объекта, используйте <xref:System.Type.GetType%2A?displayProperty=nameWithType> метод.  
  
 `GetType` Оператор может быть полезно в следующих случаях:  
  
-   Для доступа к метаданные для типа во время выполнения. <xref:System.Type> Предоставляет метаданные, такие как члены типа и сведения о развертывании. Это необходимо, например, чтобы отобразить сборку. Дополнительные сведения см. в разделе <xref:System.Reflection?displayProperty=nameWithType>.  
  
-   Вы хотите сравнить две ссылки на объект для просмотра, если они ссылаются на экземпляры того же типа. Если они есть, `GetType` возвращает ссылки на один и тот же <xref:System.Type> объекта.  
  
## <a name="example"></a>Пример  
 В приведенных ниже примерах `GetType` оператор используется.  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)

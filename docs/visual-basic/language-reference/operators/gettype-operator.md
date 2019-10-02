---
title: Оператор GetType (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 2e3e05973f2ef72fef5e429bc98cc58b4b21f2c2
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592153"
---
# <a name="gettype-operator-visual-basic"></a>Оператор GetType (Visual Basic)
Возвращает объект <xref:System.Type> для указанного типа. Объект <xref:System.Type> предоставляет сведения о типе, например его свойствах, методах и событиях.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---|---|  
|`typename`|Имя типа, для которого требуется получить сведения.|  
  
## <a name="remarks"></a>Примечания  
 Оператор `GetType` возвращает объект <xref:System.Type> для указанного `typename`. Имя любого определенного типа можно передать в `typename`. Это поведение характеризуется следующим образом.  
  
- Любой тип данных Visual Basic, например `Boolean` или `Date`.  
  
- Любой .NET Framework класс, структура, модуль или интерфейс, например <xref:System.ArgumentException?displayProperty=nameWithType> или <xref:System.Double?displayProperty=nameWithType>.  
  
- Любой класс, структура, модуль или интерфейс, определенный приложением.  
  
- Любой массив, определенный приложением.  
  
- Любой делегат, определенный приложением.  
  
- Любое перечисление, определенное Visual Basic, .NET Framework или вашего приложения.  
  
 Если требуется получить объект типа объектной переменной, используйте метод <xref:System.Type.GetType%2A?displayProperty=nameWithType>.  
  
 Оператор `GetType` может быть полезен в следующих случаях:  
  
- Необходимо получить доступ к метаданным для типа во время выполнения. Объект <xref:System.Type> предоставляет метаданные, такие как члены типов и сведения о развертывании. Это необходимо, например, для отражения сборки. Дополнительные сведения см. в разделе <xref:System.Reflection?displayProperty=nameWithType>.  
  
- Необходимо сравнить две ссылки на объект, чтобы определить, ссылаются ли они на экземпляры одного типа. В противном случае `GetType` возвращает ссылки на один и тот же объект <xref:System.Type>.  
  
## <a name="example"></a>Пример  
 В следующих примерах показано использование оператора `GetType`.  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>См. также

- [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)

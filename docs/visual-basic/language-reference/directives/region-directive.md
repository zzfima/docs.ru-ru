---
title: '#Директива Region'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: 4cf9b103486378d001b588aa285f590980b51bb8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343797"
---
# <a name="region-directive"></a>Директива #Region

Сворачивает и скрывает разделы кода в файлах Visual Basic.  
  
## <a name="syntax"></a>Синтаксис  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`identifier_string`|Обязательно. Строка, которая выступает в качестве заголовка области, если он свернут. По умолчанию области свернуты.|  
|`#End Region`|Завершает блок `#Region`.|  
  
## <a name="remarks"></a>Примечания  

 Используйте директиву `#Region`, чтобы указать блок кода, который можно разворачивать и сворачивать с помощью функции структурирования в редакторе кода Visual Studio. Вы можете разместить или *вложить*области внутри других регионов, чтобы сгруппировать похожие регионы.  
  
## <a name="example"></a>Пример  

 В этом примере используется директива `#Region`.  
  
 [!code-vb[VbVbalrConditionalComp#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>См. также

- [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Структура](/visualstudio/ide/outlining)
- [Практическое руководство. Сворачивание и скрытие частей кода](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)

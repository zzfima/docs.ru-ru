---
title: "#Указание области | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Region
- vb.#Region
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1c429602a7eee27944f58256992879d25d533d34
ms.lasthandoff: 03/13/2017

---
# <a name="region-directive"></a>#Указание области
Сворачивает и скрывает разделы кода в файлах Visual Basic.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      #Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`identifier_string`|Обязательный. Строка, которая выступает в качестве заголовка области, если он свернут. По умолчанию области свернуты.|  
|`#End Region`|Завершает блок `#Region`.|  
  
## <a name="remarks"></a>Примечания  
 Используйте директиву `#Region`, чтобы указать блок кода, который можно разворачивать и сворачивать с помощью функции структурирования в редакторе кода Visual Studio. Можно поместить или *вложить*, регионов для группировки с аналогичными областями вместе с другими областями.  
  
## <a name="example"></a>Пример  
 В этом примере используется директива `#Region`.  
  
 [!code-vb[VbVbalrConditionalComp&#4;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [#If... Then... #Else директивы](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Структурирование](https://docs.microsoft.com/visualstudio/ide/outlining)   
 [Практическое руководство. Сворачивание и скрытие частей кода](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)

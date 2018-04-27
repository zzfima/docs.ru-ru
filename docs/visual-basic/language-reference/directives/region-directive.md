---
title: '#Указание области'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83ceac7d73eff23e16c5f6efb1c4eb8a2210ee2c
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
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
 Используйте директиву `#Region`, чтобы указать блок кода, который можно разворачивать и сворачивать с помощью функции структурирования в редакторе кода Visual Studio. Можно размещать или *вкладывать друг в друга*, областей в другие области для группировки с похожими областями.  
  
## <a name="example"></a>Пример  
 В этом примере используется директива `#Region`.  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Директивы #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [Структура](/visualstudio/ide/outlining)  
 [Практическое руководство. Сворачивание и скрытие частей кода](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)

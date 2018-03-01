---
title: "Невозможно завершить операцию: конечный каталог находится внутри исходного"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0a17877b2335ee010a97f0b522bd4c399867cd7d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>Невозможно завершить операцию: конечный каталог находится внутри исходного
Циклическая операция не удалась. Циклические операции являются бесконечными циклами и поэтому не могут завершиться. Например, объект A может попытаться наследоваться от объекта B, который в свою очередь наследуется от объекта A.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   При наследовании убедитесь в отсутствии циклических ссылок.  
  
## <a name="see-also"></a>См. также  
 [Типы ошибок](../../visual-basic/programming-guide/language-features/error-types.md)  
 [Общие сведения об отладке: точки останова](http://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)

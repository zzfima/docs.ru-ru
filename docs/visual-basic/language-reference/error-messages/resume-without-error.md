---
title: "Выполнение оператора Resume без ошибки"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f86361b1e5310359288a97c5f41f017a344c30b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="resume-without-error"></a>Выполнение оператора Resume без ошибки
Объект `Resume` инструкции обнаружен вне кода обработки ошибок, или код выполнил переход в обработчик ошибок, даже если ошибок не было.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Переместить `Resume` инструкции в обработчик ошибок или удалите его.  
  
2.  Переход к меткам не может выполняться в рамках процедуры, поэтому следует выполнить поиск процедуры для метки, которая определяет обработчик ошибок. Если обнаружена повторяющаяся метка, указанный в качестве целевого объекта `GoTo` инструкции, которые не `On Error GoTo` инструкции, измените метку строки, чтобы с его намеченной цели.  
  
## <a name="see-also"></a>См. также  
 [Оператор Resume](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)

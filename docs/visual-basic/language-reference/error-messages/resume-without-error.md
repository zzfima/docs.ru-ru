---
title: Выполнение оператора Resume без ошибки
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 61332486b20af66af24eac06b222a38353578c16
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300909"
---
# <a name="resume-without-error"></a>Выполнение оператора Resume без ошибки
Объект `Resume` инструкции обнаружен вне кода обработки ошибок, или код выполнил переход в обработчик ошибок, несмотря на то, что ошибок не было.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Переместить `Resume` инструкции в обработчик ошибок или удалите его.  
  
2. Переход к меткам не может выполняться в рамках процедуры, выполните поиск процедура метку, идентифицирующую обработчика ошибок. Если вы нашли повторяющуюся метку, указанный в качестве целевого объекта `GoTo` инструкцию, которая не `On Error GoTo` инструкции, измените метку строки, чтобы с его намеченной цели.  
  
## <a name="see-also"></a>См. также

- [Оператор Resume](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Оператор On Error](../../../visual-basic/language-reference/statements/on-error-statement.md)

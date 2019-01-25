---
title: Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 9e018f4babd3ec6b212673494c6ae30f13c49737
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608853"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a>Для предложения Handles требуется переменная WithEvents, определенная в содержащем типе или одном из его базовых типов
Не предоставлен `WithEvents` переменных в вашей `Handles` предложение. `Handles` Ключевое слово в конце объявления процедуры приводит к его для обработки событий, вызванных объектной переменной, объявленной с помощью `WithEvents` ключевое слово.  
  
 **Идентификатор ошибки:** BC30506  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Укажите необходимую `WithEvents` переменной.  
  
## <a name="see-also"></a>См. также
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)

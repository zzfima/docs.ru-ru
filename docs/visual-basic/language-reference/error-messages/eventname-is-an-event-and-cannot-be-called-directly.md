---
title: "&#39; &lt;eventname&gt;&#39; является событием и не может вызываться напрямую"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords: BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb987c957a28aa37c40ad975b945c20da4690f6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39; &lt;eventname&gt;&#39; является событием и не может вызываться напрямую
"<`eventname`>" является событием и поэтому не может вызываться напрямую. Используйте `RaiseEvent` оператор для вызова события.  
  
 При вызове процедуры указывается событие имени процедуры. Обработчик событий — это процедура, но само событие является сигнальным устройством, которое должно быть создано и обработано.  
  
 **Идентификатор ошибки:** BC32022  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Используйте `RaiseEvent` инструкции для генерации события и вызова процедуры или процедуры его обработки.  
  
## <a name="see-also"></a>См. также  
 [Оператор RaiseEvent](../../../visual-basic/language-reference/statements/raiseevent-statement.md)

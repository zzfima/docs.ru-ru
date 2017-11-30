---
title: "Событие &#39; &lt;имя_события1&gt;&#39; не может реализовать событие &#39;&lt; имя_события2&gt;&#39; на интерфейс &#39;&lt; интерфейс&gt;&#39; поскольку их делегируемые типы &#39;&lt; delegate1&gt;&#39; и &#39;&lt; delegate2&gt;&#39; не совпадают"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords: BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b0fcbbf8a6e23270e4dcbf9d813c773e1522a92a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a>Событие &#39; &lt;имя_события1&gt;&#39; не может реализовать событие &#39;&lt; имя_события2&gt;&#39; на интерфейс &#39;&lt; интерфейс&gt;&#39; поскольку их делегируемые типы &#39;&lt; delegate1&gt;&#39; и &#39;&lt; delegate2&gt;&#39; не совпадают
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]не удается реализовать событие, поскольку тип делегата события не соответствует типу делегата события интерфейса. Эта ошибка может возникнуть при определении нескольких событий в интерфейсе и последующей попытке их совместной реализации с использованием одного события. Событие может реализовывать два или более событий, только если все они объявлены с помощью синтаксиса `As` и указывают один и тот же тип делегата.  
  
 **Идентификатор ошибки:** BC31423  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Реализуйте события по отдельности.  
  
     —или—  
  
-   Определите события в интерфейсе, используя `As` синтаксис и указать тот же тип делегата.  
  
## <a name="see-also"></a>См. также  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [События](../../../visual-basic/programming-guide/language-features/events/index.md)

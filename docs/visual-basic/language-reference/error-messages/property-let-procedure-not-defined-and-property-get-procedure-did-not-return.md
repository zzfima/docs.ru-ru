---
title: Процедура свойства let не определена, а процедура свойства get не вернула объект
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID451
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b043ca698a9c90afd41de90c7dbc5879ae7de623
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="property-let-procedure-not-defined-and-property-get-procedure-did-not-return-an-object"></a>Процедура свойства let не определена, а процедура свойства get не вернула объект
Некоторые свойства, методы и операции применимы только к `Collection` объектов. Указанные операция или свойство применимы только к коллекциям, но объект не является коллекцией.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте правильность написания имени объекта или свойства или убедитесь, что объект является `Collection` объекта.  
  
2.  Посмотрите на `Add` метод, используемый для добавления в коллекцию, чтобы убедитесь, что синтаксис правильный, и все идентификаторы, правильность написания.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Collection>

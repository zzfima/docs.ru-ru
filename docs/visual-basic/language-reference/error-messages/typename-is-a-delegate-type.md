---
title: "&#39; &lt;typename&gt;&#39; является типом делегата"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords: BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9428f0ac321b90e36d4d987381ed69b6c968894c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-is-a-delegate-type"></a>&#39; &lt;typename&gt;&#39; является типом делегата
"\<typename >" является типом делегата. Конструкция делегата позволяет использовать только одно выражение AddressOf как список аргументов. Часто выражение AddressOf может использоваться вместо конструкции делегата.  
  
 Объект `New` создании экземпляра класса делегата передает недопустимый список аргументов для конструктора делегата.  
  
 Можно задать только одно `AddressOf` выражения при создании нового экземпляра делегата.  
  
 Эта ошибка может возникнуть, если не передать аргументы конструктора делегата, если передать несколько аргументов, или если передается один аргумент, не является допустимым `AddressOf` выражение.  
  
 **Идентификатор ошибки:** BC32008  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Использовать отдельный `AddressOf` выражение в списке аргументов для класса делегата в `New` предложения.  
  
## <a name="see-also"></a>См. также  
 [Оператор New](../../../visual-basic/language-reference/operators/new-operator.md)  
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Практическое руководство. Вызов метода делегата](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)

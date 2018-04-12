---
title: Недопустимый порядковый номер
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d31d0fba19cc16004c0b56786af30603d0c509ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ordinal-is-not-valid"></a>Недопустимый порядковый номер
При вызове в библиотеке динамической компоновки (DLL) использовался использовать номер, а не имя процедуры, с помощью `#num` синтаксиса. Эта ошибка имеет следующие возможные причины:  
  
-   Попытка преобразовать `#num` выражение в порядковый.  
  
-   `#num` Указанного не соответствует ни одной функции в DLL.  
  
-   Библиотека типов имеет недопустимое объявление причиной внутреннего использования недопустимого порядкового номера.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что выражение представляет допустимый номер или вызовите процедуру по имени.  
  
2.  Убедитесь, что `#num` определяет допустимую функцию в DLL.  
  
3.  Изолируйте вызов процедуры, вызывающей ошибку код комментарием. Запись `Declare` инструкции для процедуры и сообщите об ошибке разработчику библиотеки типов.  
  
## <a name="see-also"></a>См. также  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)

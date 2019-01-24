---
title: Тип &#39; &lt;typename&gt; &#39; не имеет конструкторов
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 8a13451956b8afb1bf733c6faa218eadf4255495
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511112"
---
# <a name="type-39lttypenamegt39-has-no-constructors"></a>Тип &#39; &lt;typename&gt; &#39; не имеет конструкторов
Тип не поддерживает вызов в `Sub New()`. Одной из возможных причин является повреждение компилятора или двоичного файла.  
  
 **Идентификатор ошибки:** BC30251  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Если тип находится в другом проекте или в заданном ссылкой файле, переустановите этот проект или файл.  
  
2.  Если тип находится в том же самом проекте, перекомпилируйте сборку, содержащую тип.  
  
3.  Если ошибка повторяется, переустановите компилятор Visual Basic.  
  
4.  Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.  
  
## <a name="see-also"></a>См. также
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Обращайтесь к нам](/visualstudio/ide/talk-to-us)

---
title: В типе <typename> отсутствуют конструкторы
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 506b69f1db12a51217d10ad261b1f1a44bfb2008
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198158"
---
# <a name="type-typename-has-no-constructors"></a>Тип "\<TypeName >" не имеет конструкторов
Тип не поддерживает вызов в `Sub New()`. Одной из возможных причин является повреждение компилятора или двоичного файла.  
  
 **Идентификатор ошибки:** BC30251  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Если тип находится в другом проекте или в заданном ссылкой файле, переустановите этот проект или файл.  
  
2. Если тип находится в том же самом проекте, перекомпилируйте сборку, содержащую тип.  
  
3. Если ошибка повторяется, переустановите компилятор Visual Basic.  
  
4. Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.  
  
## <a name="see-also"></a>См. также

- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Обращайтесь к нам](/visualstudio/ide/feedback-options)

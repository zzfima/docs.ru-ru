---
title: В типе <typename> отсутствуют конструкторы
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 8564499b9ff55514179314217b7d40d8d3cdf6a2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311658"
---
# <a name="type-typename-has-no-constructors"></a>Тип "\<typename >" не имеет конструкторов
Тип не поддерживает вызов в `Sub New()`. Одной из возможных причин является повреждение компилятора или двоичного файла.  
  
 **Идентификатор ошибки:** BC30251  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Если тип находится в другом проекте или в заданном ссылкой файле, переустановите этот проект или файл.  
  
2. Если тип находится в том же самом проекте, перекомпилируйте сборку, содержащую тип.  
  
3. Если ошибка повторяется, переустановите компилятор Visual Basic.  
  
4. Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.  
  
## <a name="see-also"></a>См. также

- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Обращайтесь к нам](/visualstudio/ide/talk-to-us)

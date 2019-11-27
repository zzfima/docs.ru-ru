---
title: Подпрограмма или функция не определена
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 8b81460eccb6be8baa2ea7bc68d0f80c9d16398e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349580"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub или Function не определена (Visual Basic)
Для вызова необходимо определить `Sub` или `Function`. Возможные причины этой ошибки:  
  
- Ошибка написания имени процедуры.  
  
- Попытка вызвать процедуру из другого проекта без явного добавления ссылки на этот проект в диалоговом окне " **ссылки** ".  
  
- Указание процедуры, которая не является видимой для вызывающей процедуры.  
  
- Объявление подпрограммы библиотеки динамической компоновки Windows (DLL) или служебной программы-ресурса для Macintosh, которая не находится в указанной библиотеке или ресурсе кода.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что имя процедуры написано правильно.  
  
2. Найдите имя проекта, содержащего процедуру, которую необходимо вызвать, в диалоговом окне **ссылки** . Если она не отображается, нажмите кнопку **Обзор** , чтобы найти ее. Установите флажок слева от имени проекта и нажмите кнопку **ОК**.  
  
3. Проверьте имя подпрограммы.  
  
## <a name="see-also"></a>См. также

- [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Управление ссылками в проекте](/visualstudio/ide/managing-references-in-a-project)
- [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)

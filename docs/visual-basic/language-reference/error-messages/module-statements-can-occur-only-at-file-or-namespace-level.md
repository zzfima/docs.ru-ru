---
title: '&#39;Модуль&#39; операторы могут использоваться только на уровне файлов и пространств имен'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 53199c2d7081445dc5490d5c54c98f93ee7522eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a>&#39;Модуль&#39; операторы могут использоваться только на уровне файлов и пространств имен
`Module` операторы должны находиться в верхней части файла исходного кода сразу после `Option` и `Imports` инструкции, глобальных атрибутов и объявлений пространств имен, но перед всеми остальными объявлениями.  
  
 **Идентификатор ошибки:** BC30617  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Переместите `Module` в начало имен объявления или исходного файла.  
  
## <a name="see-also"></a>См. также  
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)

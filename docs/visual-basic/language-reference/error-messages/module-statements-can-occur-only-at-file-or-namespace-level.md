---
title: '&#39;Модуль&#39; операторы могут использоваться только на уровне файлов или пространств имен'
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: bdbf8df5942e9df4b9696aeea4e3492121efe21a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746316"
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a>&#39;Модуль&#39; операторы могут использоваться только на уровне файлов или пространств имен
`Module` операторы должны находиться в начале файла исходного кода сразу же после `Option` и `Imports` инструкции, глобальных атрибутов и деклараций пространств имен, но перед всеми объявлениями.  
  
 **Идентификатор ошибки:** BC30617  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Переместите оператор `Module` в начало объявления пространства имен или исходного файла.  
  
## <a name="see-also"></a>См. также
- [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)

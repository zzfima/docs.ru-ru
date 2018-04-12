---
title: '&#39; Модуль &#39; операторы могут использоваться только на уровне файлов и пространств имен'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 61fe12fbd7d20e6cd2b6bc464e7fc3293150213b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="39module39-statements-can-occur-only-at-file-or-namespace-level"></a>&#39; Модуль &#39; операторы могут использоваться только на уровне файлов и пространств имен
`Module`операторы должны находиться в верхней части файла исходного кода сразу после `Option` и `Imports` инструкции, глобальных атрибутов и объявлений пространств имен, но перед всеми остальными объявлениями.  
  
 **Идентификатор ошибки:** BC30617  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Переместите `Module` в начало имен объявления или исходного файла.  
  
## <a name="see-also"></a>См. также  
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)

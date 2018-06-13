---
title: Ошибка при загрузке библиотеки DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: ac21c4d52b248025ee26bac3e511bb5b0a0b668e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584687"
---
# <a name="error-in-loading-dll-visual-basic"></a>Ошибка при загрузке библиотеки DLL (Visual Basic)
Библиотеки динамической компоновки (DLL) — это библиотека, указанный в `Lib` предложения `Declare` инструкции. Среди возможных причин этой ошибки:  
  
-   Файл не является исполняемой программой DLL.  
  
-   Файл не является Библиотекой Microsoft Windows.  
  
-   DLL ссылается на другой библиотеке DLL, не существует.  
  
-   DLL или DLL, на которую указывает ссылка не находится в каталоге, указанном в пути.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если файл исходного текста файла и поэтому не исполняемым файлом DLL, ее необходимо компиляции и компоновки в форму исполняемого файла DLL.  
  
-   Если файл не является Библиотекой Microsoft Windows, получите эквивалентное Microsoft Windows.  
  
-   Если DLL ссылается на другой библиотеки DLL, которая не указан, получите указанной библиотеке DLL и сделать ее доступной.  
  
-   Если DLL или DLL, на которую указывает ссылка не находится в каталоге, указанном в пути, следует перенести DLL к указанному каталогу.  
  
## <a name="see-also"></a>См. также  
 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)

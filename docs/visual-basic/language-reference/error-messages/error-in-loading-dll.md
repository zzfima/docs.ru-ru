---
title: Ошибка при загрузке библиотеки DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: c3f88a5a3c37c89d23055aa413957b2add38ed67
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816906"
---
# <a name="error-in-loading-dll-visual-basic"></a>Ошибка при загрузке библиотеки DLL (Visual Basic)
Это библиотека динамической компоновки (DLL) — это библиотека, указанный в `Lib` предложении `Declare` инструкции. Среди возможных причин этой ошибки:  
  
-   Файл не является исполняемой программой DLL.  
  
-   Файл не является Библиотекой Microsoft Windows.  
  
-   DLL ссылается на другой библиотеке DLL, не существует.  
  
-   DLL или DLL, на которую указывает ссылка отсутствует в каталоге, указанном в пути.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если файл источника текстовый файл и поэтому не исполняемый файл DLL, он должен будет компилироваться и собираться в форму исполняемого файла DLL.  
  
-   Если файл не является Библиотекой Microsoft Windows, получите эквивалентное Microsoft Windows.  
  
-   Если библиотека DLL ссылается другая библиотека DLL, которая отсутствует, получите указанной библиотеке DLL и сделать его доступным.  
  
-   Если DLL или DLL, на которую указывает ссылка не находится в каталоге, указанном в пути, переместите библиотеку DLL в каталог, на который указывает ссылка.  
  
## <a name="see-also"></a>См. также

- [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)

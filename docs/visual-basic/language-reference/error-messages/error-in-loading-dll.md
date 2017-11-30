---
title: "Ошибка при загрузке библиотеки DLL (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cc557dcc6709178b6519adb56f31debcbd1d1c39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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

---
title: "&#39; Строки &#39; инструкции, больше не поддерживаются (Ошибка компилятора Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords: BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d2db5dc786749360dfcf6789f12b5659d5713fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39line39-statements-are-no-longer-supported-visual-basic-compiler-error"></a>&#39; Строки &#39; инструкции, больше не поддерживаются (Ошибка компилятора Visual Basic)
Операторы Line больше не поддерживаются. Функциональность файлового ввода-вывода доступна как `Microsoft.VisualBasic.FileSystem.LineInput` и графические возможности доступны в качестве `System.Drawing.Graphics.DrawLine`.  
  
 **Идентификатор ошибки:** BC30830  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Если выполняется доступ к файлу, используйте `Microsoft.VisualBasic.FileSystem.LineInput`.  
  
2.  Если выполняется вывод графики, используйте `System.Drawing.Graphics.Drawline`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO>  
 <xref:System.Drawing>  
 [Доступ к файлам с помощью Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)

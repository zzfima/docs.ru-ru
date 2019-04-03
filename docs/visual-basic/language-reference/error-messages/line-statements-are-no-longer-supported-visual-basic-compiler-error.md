---
title: Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 7616bcdc39ab479049586534fac22f1e2d96a700
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831843"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a>Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic)
Операторы Line больше не поддерживаются. Функциональность файлового ввода-вывода доступна как `Microsoft.VisualBasic.FileSystem.LineInput` и графические функции доступен в виде `System.Drawing.Graphics.DrawLine`.  
  
 **Идентификатор ошибки:** BC30830  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Если выполняется доступ к файлу, используйте `Microsoft.VisualBasic.FileSystem.LineInput`.  
  
2.  Если выполняется вывод графики, используйте `System.Drawing.Graphics.Drawline`.  
  
## <a name="see-also"></a>См. также

- <xref:System.IO>
- <xref:System.Drawing>
- [Доступ к файлам с помощью Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)

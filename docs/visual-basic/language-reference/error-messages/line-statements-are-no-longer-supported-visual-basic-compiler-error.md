---
title: Операторы Line больше не поддерживаются (ошибка компилятора Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 17025e9a3c87d84a10ddaa7aeef616d985143879
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283239"
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

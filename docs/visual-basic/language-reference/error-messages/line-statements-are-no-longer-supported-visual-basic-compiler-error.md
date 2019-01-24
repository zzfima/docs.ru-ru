---
title: '&#39;Строки&#39; инструкции больше не поддерживаются (Ошибка компилятора Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 36226cc371ffb8a51cb8d0f918952f1c717aea10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702983"
---
# <a name="39line39-statements-are-no-longer-supported-visual-basic-compiler-error"></a>&#39;Строки&#39; инструкции больше не поддерживаются (Ошибка компилятора Visual Basic)
Операторы Line больше не поддерживаются. Функциональность файлового ввода-вывода доступна как `Microsoft.VisualBasic.FileSystem.LineInput` и графические функции доступен в виде `System.Drawing.Graphics.DrawLine`.  
  
 **Идентификатор ошибки:** BC30830  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Если выполняется доступ к файлу, используйте `Microsoft.VisualBasic.FileSystem.LineInput`.  
  
2.  Если выполняется вывод графики, используйте `System.Drawing.Graphics.Drawline`.  
  
## <a name="see-also"></a>См. также
- <xref:System.IO>
- <xref:System.Drawing>
- [Доступ к файлам с помощью Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)

---
title: /utf8output (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 23c7c308865a6b6afb07443a42090fff3d9e2efb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="utf8output-visual-basic"></a>/utf8output (Visual Basic)
Отображает выходные данные компилятора в кодировке UTF-8.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательно. Значение по умолчанию для этого параметра — `/utf8output-`, что означает, что выходные данные компилятора не использует кодировку UTF-8. Указание `/utf8output` же эффект достигается указанием `/utf8output+`.  
  
## <a name="remarks"></a>Примечания  
 В некоторых конфигурациях для различных языков выходные данные компилятора не может неправильно отображаться на консоли. В этом случае следует использовать `/utf8output` и перенаправлять выходные данные компилятора в файл.  
  
> [!NOTE]
>  `/utf8output` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` , а компилятор для отображения вывода с использованием кодировки UTF-8.  
  
```  
vbc /utf8output in.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

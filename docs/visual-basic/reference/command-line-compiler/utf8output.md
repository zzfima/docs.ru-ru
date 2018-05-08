---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 753c92cdf2124ee7fb1b471c7bc543b6db6f3daa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
Отображает выходные данные компилятора в кодировке UTF-8.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный. Значение по умолчанию для этого параметра — `-utf8output-`, что означает, что выходные данные компилятора не использует кодировку UTF-8. Указание `-utf8output` же эффект достигается указанием `-utf8output+`.  
  
## <a name="remarks"></a>Примечания  
 В некоторых конфигурациях для различных языков выходные данные компилятора не может неправильно отображаться на консоли. В этом случае следует использовать `-utf8output` и перенаправлять выходные данные компилятора в файл.  
  
> [!NOTE]
>  `-utf8output` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` , а компилятор для отображения вывода с использованием кодировки UTF-8.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

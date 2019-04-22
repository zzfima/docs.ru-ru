---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 75369c3bcb19afbf98bfb80bc3e439f996d2a9d0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833652"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
Отображает выходные данные компилятора в кодировке UTF-8.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный параметр. Значение по умолчанию для этого параметра — `-utf8output-`, что означает, что выходные данные компилятора не использует кодировку UTF-8. Указание `-utf8output` дает тот же результат, что и указание `-utf8output+`.  
  
## <a name="remarks"></a>Примечания  
 В некоторых конфигурациях для различных языков выходные данные компилятора, могут отображаться правильно в консоли. В таких ситуациях используйте `-utf8output` и перенаправления выходных данных компилятора в файл.  
  
> [!NOTE]
>  `-utf8output` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и компилятор для отображения выходных данных с использованием кодировки UTF-8.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

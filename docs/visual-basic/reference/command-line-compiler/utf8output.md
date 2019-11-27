---
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 5cdc60888cd872940afc1b03febd879bb6d87c2e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350841"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
Отображает выходные данные компилятора в кодировке UTF-8.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Аргументы  
 `+` &#124; `-`  
 Необязательный элемент. Значение по умолчанию для этого параметра — `-utf8output-`, то есть выходные данные компилятора не используют кодировку UTF-8. Указание `-utf8output` дает тот же результат, что и указание `-utf8output+`.  
  
## <a name="remarks"></a>Примечания  
 В некоторых международных конфигурациях вывод компилятора не может правильно отображаться в консоли. В таких ситуациях используйте `-utf8output` и перенаправьте выходные данные компилятора в файл.  
  
> [!NOTE]
> Параметр `-utf8output` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и направляет компилятор для вывода выходных данных в кодировке UTF-8.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

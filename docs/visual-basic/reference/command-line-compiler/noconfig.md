---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: c57ed1699d110959e9faf3dc3d43bcc200851c1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005432"
---
# <a name="-noconfig"></a>-noconfig
Указывает, что компилятор не должен автоматически ссылаться на часто используемые .NET Framework сборки или импортировать пространства имен `System` и `Microsoft.VisualBasic`.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр `-noconfig` указывает компилятору не компилировать файл Vbc. rsp, который находится в том же каталоге, что и файл Vbc. exe. Файл Vbc. rsp ссылается на часто используемые сборки .NET Framework и импортирует пространства имен `System` и `Microsoft.VisualBasic`. Компилятор неявно ссылается на сборку System. dll, если не указан параметр `-nostdlib`. Параметр `-nostdlib` указывает компилятору не компилировать с Vbc. rsp или автоматически ссылаться на сборку System. dll.  
  
> [!NOTE]
> Ссылки на сборки mscorlib. dll и Microsoft. VisualBasic. dll всегда существуют.  
  
 Можно изменить файл Vbc. rsp, указав дополнительные параметры компилятора, которые должны включаться в каждую компиляцию Vbc. exe (кроме случая, когда указан параметр `-noconfig`). Дополнительные сведения см. в документации синтаксиса [@ (указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 Компилятор обрабатывает параметры, переданные в команду `vbc`, в последнюю очередь. Таким образом, любой параметр в командной строке переопределяет параметр того же параметра в файле Vbc. rsp.  
  
> [!NOTE]
> Параметр `-noconfig` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также

- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [@ (указание файла ответов)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)

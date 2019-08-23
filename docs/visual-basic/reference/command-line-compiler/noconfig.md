---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: ca184fa130d62dc118d0de551ac58f3165064029
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964396"
---
# <a name="-noconfig"></a>-noconfig
Указывает, что компилятор не должен автоматически ссылаться на часто используемые .NET Framework сборки или импортировать `System` пространства имен и. `Microsoft.VisualBasic`  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>Примечания  
 `-noconfig` Параметр указывает компилятору не компилировать файл Vbc. rsp, который находится в том же каталоге, что и файл Vbc. exe. Файл Vbc. rsp ссылается на часто используемые сборки .NET Framework и импортирует `System` пространства имен и. `Microsoft.VisualBasic` Компилятор неявно ссылается на сборку System. dll, `-nostdlib` если не указан параметр. `-nostdlib` Параметр указывает компилятору не компилировать с Vbc. rsp или автоматически ссылаться на сборку System. dll.  
  
> [!NOTE]
> Ссылки на сборки mscorlib. dll и Microsoft. VisualBasic. dll всегда существуют.  
  
 Можно изменить файл Vbc. rsp, указав дополнительные параметры компилятора, которые должны включаться в каждую компиляцию Vbc. exe (за исключением случаев, `-noconfig` когда указан параметр). Дополнительные сведения см. в документации синтаксиса [@ (указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 Компилятор обрабатывает параметры, переданные в `vbc` команду последними. Таким образом, любой параметр в командной строке переопределяет параметр того же параметра в файле Vbc. rsp.  
  
> [!NOTE]
> Этот `-noconfig` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также

- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [@ (указание файла ответов)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)

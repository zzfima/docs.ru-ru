---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: b707899c845b6b08e008fe229497f682c930044a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588847"
---
# <a name="-noconfig"></a>-noconfig
Указывает, что компилятор должен автоматически ссылки на часто используемые сборки .NET Framework или импортировать `System` и `Microsoft.VisualBasic` пространства имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>Примечания  
 `-noconfig` Указывает компилятору не выполнять компиляцию с помощью файла Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe. Файл Vbc.rsp ссылается на часто используемые сборки .NET Framework и импортирует `System` и `Microsoft.VisualBasic` пространства имен. Компилятор неявно ссылается на сборку System.dll, если не `-nostdlib` параметра. `-nostdlib` Параметр указывает компилятору не компилировать с Vbc.rsp или автоматически ссылаются на сборки System.dll.  
  
> [!NOTE]
>  Всегда существуют ссылки на сборки библиотеки Mscorlib.dll и Microsoft.VisualBasic.dll.  
  
 Можно изменить файл Vbc.rsp и указать дополнительные параметры компилятора, которые должны быть включены в каждую компиляцию Vbc.exe (за исключением при указании `-noconfig` параметр). Дополнительные сведения см. в документации синтаксиса [@ (указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 Компилятор обрабатывает параметры, передаваемые `vbc` последней команды. Таким образом любой параметр командной строки переопределяет значение аналогичного параметра в файл Vbc.rsp.  
  
> [!NOTE]
>  `-noconfig` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также

- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [@ (указание файла ответов)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-ссылке (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)

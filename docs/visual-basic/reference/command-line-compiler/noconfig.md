---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: bce2d98a8915e80cdecd7b67029b0c872cf70140
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37959583"
---
# <a name="-noconfig"></a>-noconfig
Указывает, что компилятор не должен ссылаться автоматически часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки или импорта `System` и `Microsoft.VisualBasic` пространства имен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>Примечания  
 `-noconfig` Указывает компилятору не выполнять компиляцию с помощью файла Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe. Файл Vbc.rsp ссылается на часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки и импортируемые объекты `System` и `Microsoft.VisualBasic` пространства имен. Компилятор неявно ссылается на сборку System.dll, если не `-nostdlib` параметра. `-nostdlib` Параметр указывает компилятору не компилировать с Vbc.rsp или автоматически ссылаются на сборки System.dll.  
  
> [!NOTE]
>  Всегда существуют ссылки на сборки библиотеки Mscorlib.dll и Microsoft.VisualBasic.dll.  
  
 Можно изменить файл Vbc.rsp и указать дополнительные параметры компилятора, которые должны быть включены в каждую компиляцию Vbc.exe (за исключением при указании `-noconfig` параметр). Дополнительные сведения см. в документации синтаксиса [@ (указание файла ответа)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 Компилятор обрабатывает параметры, передаваемые `vbc` последней команды. Таким образом любой параметр командной строки переопределяет значение аналогичного параметра в файл Vbc.rsp.  
  
> [!NOTE]
>  `-noconfig` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="see-also"></a>См. также  
 [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [@ (указание файла ответов)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)  
 [-ссылке (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)

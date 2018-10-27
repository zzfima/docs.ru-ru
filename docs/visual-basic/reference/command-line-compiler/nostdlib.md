---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 957eca6066a316a4f4daf7e6de972df98082c26c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183300"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Указывает компилятору не ссылаться на стандартные библиотеки автоматически.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a>Примечания  
 `-nostdlib` Удаляет автоматическую ссылку на сборку System.dll и предотвращает чтение файла Vbc.rsp компилятор. Файл Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe, ссылается на часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки и импортируемые объекты `System` и `Microsoft.VisualBasic` пространства имен.  
  
> [!NOTE]
>  Всегда существуют ссылки на сборки библиотеки Mscorlib.dll и Microsoft.VisualBasic.dll.  
  
> [!NOTE]
>  `-nostdlib` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` без ссылок на стандартные библиотеки. Необходимо задать `_MYTYPE` константы условной компиляции в строку «Empty», чтобы удалить `My` объекта.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)

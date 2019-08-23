---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 19a70e500f6b75fd003bdb798f242cddb3926935
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964349"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Приводит к тому, что компилятор не будет автоматически ссылаться на стандартные библиотеки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a>Примечания  
 `-nostdlib` Параметр удаляет автоматическую ссылку на сборку System. dll и запрещает компилятору считывать файл Vbc. rsp. Файл Vbc. rsp, расположенный в том же каталоге, что и файл Vbc. exe, ссылается на часто используемые .NET Framework сборки и импортирует `System` пространства имен и. `Microsoft.VisualBasic`  
  
> [!NOTE]
> Ссылки на сборки mscorlib. dll и Microsoft. VisualBasic. dll всегда существуют.  
  
> [!NOTE]
> Этот `-nostdlib` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилируется `T2.vb` без ссылок на стандартные библиотеки. `_MYTYPE` Для`My` удаления объекта необходимо задать константу условной компиляции в виде строки "Empty".  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>См. также

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)

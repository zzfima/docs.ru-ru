---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 819505df2e7d5f93302f9ed601de856e36ed7124
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005415"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
Приводит к тому, что компилятор не будет автоматически ссылаться на стандартные библиотеки.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр `-nostdlib` удаляет автоматическую ссылку на сборку System. dll и запрещает компилятору считывать файл Vbc. rsp. Файл Vbc. rsp, расположенный в том же каталоге, что и файл Vbc. exe, ссылается на часто используемые .NET Framework сборки и импортирует пространства имен `System` и `Microsoft.VisualBasic`.  
  
> [!NOTE]
> Ссылки на сборки mscorlib. dll и Microsoft. VisualBasic. dll всегда существуют.  
  
> [!NOTE]
> Параметр `-nostdlib` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` без ссылки на стандартные библиотеки. Необходимо задать константу условной компиляции `_MYTYPE` в виде строки "Empty", чтобы удалить объект `My`.  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>См. также

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)

---
title: /nostdlib (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9d76563a5b3d439495899e07ce2df59c0acd75e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="nostdlib-visual-basic"></a>/nostdlib (Visual Basic)
Указывает компилятору не ссылаться на стандартные библиотеки автоматически.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/nostdlib  
```  
  
## <a name="remarks"></a>Примечания  
 `/nostdlib` Удаляет автоматическую ссылку на сборку System.dll и запрещает компилятору считывание файла Vbc.rsp. Файл Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe — ссылается на часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки и Импортируемые пространства имен `System` и `Microsoft.VisualBasic` пространства имен.  
  
> [!NOTE]
>  Всегда создаются ссылки на сборки Mscorlib.dll и Microsoft.VisualBasic.dll.  
  
> [!NOTE]
>  `/nostdlib` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `T2.vb` без ссылок на стандартные библиотеки. Необходимо задать `_MYTYPE` константы условной компиляции на пустой строке, чтобы удалить `My` объекта.  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>См. также  
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)

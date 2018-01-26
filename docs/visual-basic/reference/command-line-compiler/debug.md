---
title: /debug (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- debug compiler switches
- /debug compiler option [Visual Basic]
- -debug compiler option [Visual Basic]
- debug compiler option [Visual Basic]
ms.assetid: c2b0bea5-1d5e-499f-9bd5-4f6c6b715ea2
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07ab386ddb456c059b6390b986ec0a880320973b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="debug-visual-basic"></a>/debug (Visual Basic)
Указывает компилятору создавать отладочную информацию и поместить ее в выходных файлах.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/debug[+ | -]  
' -or-  
/debug:[full | pdbonly]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный. Указание `+` или `/debug` указывает компилятору создавать отладочную информацию и поместить ее в PDB-файл. Указание `-` имеет тот же эффект, что и при указании не `/debug`.|  
|`full` &#124; `pdbonly`|Необязательный. Определяет тип отладочной информации, создаваемой компилятором. Если вы не укажете `/debug:pdbonly`, значение по умолчанию — `full`, что позволяет присоединить отладчик к выполняющейся программе. `pdbonly` Аргумент позволяет выполнить отладку исходного кода при запуске программы в отладчике, но только в том случае, когда исполняемой программы в отладчике отображается кода на языке ассемблера.|  
  
## <a name="remarks"></a>Примечания  
 Используйте этот параметр для создания отладочных сборок. Если вы не укажете `/debug`, `/debug+`, или `/debug:full`, нельзя отладить выходной файл программы.  
  
 По умолчанию отладочная информация не создается (`/debug-`). Для получения отладочной информации, укажите `/debug` или `/debug+`.  
  
 Сведения о настройке производительности отладки для приложения см. в разделе [Упрощение отладки образов](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
|Задание/Debug в Visual Studio интегрированной среде разработки|  
|---|  
|1.  Выберите проект в **обозревателе решений**, а затем в меню **Проект** щелкните **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Щелкните **Дополнительные параметры компиляции**.<br />4.  Измените значение в **создать отладочную информацию** поле.|  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует размещение отладочной информации в выходной файл `App.exe`.  
  
```  
vbc /debug /out:app.exe test.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

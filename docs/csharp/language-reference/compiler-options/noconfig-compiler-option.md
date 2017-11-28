---
title: "-noconfig (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2b15853cdd6ee9fe12b8b3ba3388a74e49c9701
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="noconfig-c-compiler-options"></a>/noconfig (параметры компилятора C#)
Параметр **/noconfig** указывает компилятору не выполнять компиляцию с использованием файла csc.rsp, который располагается в том же каталоге, что и файл csc.exe, и загружается из этого каталога.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/noconfig  
```  
  
## <a name="remarks"></a>Примечания  
 Файл csc.rsp содержит ссылки на все сборки, поставляемые вместе с платформой .NET Framework. Фактические ссылки, которые включает среда разработки Visual Studio .NET, зависят от типа проекта.  
  
 Вы можете изменить файл csc.rsp и указать дополнительные параметры компилятора, которые необходимо включать каждый раз при компиляции, из командной строки с помощью файла csc.exe (кроме параметра **/noconfig**).  
  
 Компилятор обрабатывает параметры, передаваемые в команду **csc**, последними. Таким образом, любой параметр командной строки переопределяет значение аналогичного параметра в файле csc.rsp.  
  
 Если не требуется, чтобы компилятор искал и использовал параметры в файле csc.rsp, укажите параметр **/noconfig**.  
  
 Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)

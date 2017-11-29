---
title: /linkresource (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e51f844695985485210a1e4bedfef7ac968326c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="linkresource-visual-basic"></a>/linkresource (Visual Basic)
Создает ссылку на управляемый ресурс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Обязательный. Файл ресурсов, ссылки на сборку. Если имя файла содержит пробелы, заключите имя в кавычки (» «).  
  
 `identifier`  
 Необязательно. Логическое имя ресурса. Имя, которое используется для загрузки ресурса. По умолчанию используется имя файла. Кроме того, можно указать, является ли файл открытым или закрытым в манифесте сборки, например: `/linkres:filename.res,myname.res,public`. По умолчанию `filename` является открытым в сборке.  
  
## <a name="remarks"></a>Примечания  
 `/linkresource` Параметр нельзя внедрить файл ресурсов в выходной файл; используйте `/resource` параметр, чтобы сделать это.  
  
 `/linkresource` Параметра необходим один из `/target` параметры отличный от `/target:module`.  
  
 Если `filename` — [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] файла ресурсов, созданным, например, с [Resgen.exe (генератор файлов ресурсов)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) или в среде разработки, он может осуществляться с помощью членов <xref:System.Resources> пространства имен. (Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager>.) Для доступа к другим ресурсам во время выполнения, используйте методы, которые начинаются с `GetManifestResource` в <xref:System.Reflection.Assembly> класса.  
  
 Имя файла может иметь любой формат файла. Например, может потребоваться сделать имеющуюся на компьютере библиотеку DLL частью сборки, поэтому ее можно разместить в глобальном кэше сборок и обеспечить к ней доступ из управляемого кода сборки.  
  
 Краткой формой `/linkresource` является `/linkres`.  
  
> [!NOTE]
>  `/linkresource` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и ссылки на файл ресурсов `Rf.resource`.  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [/ Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

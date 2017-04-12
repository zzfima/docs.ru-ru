---
title: "/ linkresource (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fafde6563340189108a879b82e7e880aca690b39
ms.lasthandoff: 03/13/2017

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
 Обязательный. Файл ресурсов, ссылку на сборку. Если имя файла содержит пробел, заключите имя в кавычки (» «).  
  
 `identifier`  
 Необязательный. Логическое имя ресурса. Имя, используемое для загрузки ресурса. Значение по умолчанию — имя файла. Кроме того, можно указать, является ли файл открытым или закрытым в манифесте сборки, например: `/linkres:filename.res,myname.res,public`. По умолчанию `filename` является открытым в сборке.  
  
## <a name="remarks"></a>Примечания  
 `/linkresource` Параметр не внедрить файл ресурсов в выходной файл; используйте `/resource` параметр, чтобы сделать это.  
  
 `/linkresource` Параметра необходим один из `/target` параметры не `/target:module`.  
  
 Если `filename` — [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] файла ресурсов, созданным, например, с [Resgen.exe (генератор файлов ресурсов)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) или в среде разработки, может осуществляться с помощью членов <xref:System.Resources>имен.</xref:System.Resources> (Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager>.)</xref:System.Resources.ResourceManager> Для доступа к другим ресурсам во время выполнения, используйте методы, которые начинаются с `GetManifestResource` в <xref:System.Reflection.Assembly>класс.</xref:System.Reflection.Assembly>  
  
 Имя файла может иметь любой формат файла. Например может потребоваться сделать собственную библиотеку DLL частью сборки, можно установить в глобальный кэш сборок и доступна из управляемого кода в сборке.  
  
 Краткая форма `/linkresource` — `/linkres`.  
  
> [!NOTE]
>  `/linkresource` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и ссылки на файл ресурсов `Rf.resource`.  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [/ Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

---
title: "/ Resource (Visual Basic) | Документы Microsoft"
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
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b46800322fd03eb2578cc558cc1d9bb78550aa61
ms.lasthandoff: 03/13/2017

---
# <a name="resource-visual-basic"></a>/resource (Visual Basic)
Внедряет управляемый ресурс в сборку.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`filename`|Обязательный. Имя файла ресурсов для внедрения в выходной файл. По умолчанию `filename` является открытым в сборке. Заключите имя файла в кавычки («»), если он содержит пробел.|  
|`identifier`|Необязательный. Логическое имя ресурса; имя, используемое для его загрузки. Значение по умолчанию — имя файла. При необходимости можно указать ли ресурс открытым или закрытым в манифесте сборки с помощью следующих: `/res:``filename.res`,`myname.res`,`public`|  
  
## <a name="remarks"></a>Примечания  
 Используйте `/linkresource` , чтобы связать ресурс и сборку, не помещая файл ресурсов в выходной файл.  
  
 Если `filename` — [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] файла ресурсов, созданным, например, с [Resgen.exe (генератор файлов ресурсов)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) или в среде разработки, может осуществляться с помощью членов <xref:System.Resources>пространства имен (см. <xref:System.Resources.ResourceManager>Дополнительные сведения).</xref:System.Resources.ResourceManager> </xref:System.Resources> Для доступа к другим ресурсам во время выполнения, используйте один из следующих способов: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, или <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.</xref:System.Reflection.Assembly.GetManifestResourceStream%2A> </xref:System.Reflection.Assembly.GetManifestResourceNames%2A> </xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>  
  
 Краткая форма `/resource` — `/res`.  
  
 Дополнительные сведения о настройке `/resource` в СРЕДЕ Visual Studio в разделе [управление ресурсами приложения (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и присоединение файла ресурсов `Rf.resource`.  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)   
 [/ linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)   
 [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

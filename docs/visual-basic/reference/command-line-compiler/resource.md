---
title: -ресурсов (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 2d7da572ecc8d7d20917eaa244eefbcd7abe61f0
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589512"
---
# <a name="-resource-visual-basic"></a>-ресурсов (Visual Basic)
Внедряет управляемый ресурс в сборку.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-resource:filename[,identifier[,public|private]]  
' -or-  
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`filename`|Обязательный. Имя файла ресурсов для внедрения в выходной файл. По умолчанию `filename` является открытым в сборке. Заключите имя файла в кавычки (» «), если он содержит пробел.|  
|`identifier`|Необязательный параметр. Логическое имя ресурса; имя, использованное для ее загрузки. По умолчанию используется имя файла. При необходимости можно указать, является ли ресурс открытым или закрытым в манифесте сборки, как и в случае со следующим: `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>Примечания  
 Используйте `-linkresource` чтобы связать ресурс со сборкой, не помещая файл ресурсов в выходной файл.  
  
 Если `filename` является файлом ресурсов .NET Framework, созданным, например, по [Resgen.exe (генератор файлов ресурсов)](../../../framework/tools/resgen-exe-resource-file-generator.md) или в среде разработки, он может осуществляться с помощью членов пространства <xref:System.Resources> пространства имен (см. <xref:System.Resources.ResourceManager> Дополнительные сведения). Чтобы получить доступ к всем остальным ресурсам во время выполнения, используйте один из следующих методов: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>, или <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 Краткой формой `-resource` является `-res`.  
  
 Сведения о настройке `-resource` в СРЕДЕ Visual Studio, см. в разделе [управлении ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и присоединение файла ресурсов `Rf.resource`.  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

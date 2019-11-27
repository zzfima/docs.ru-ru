---
title: -resource
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: a781d543dd32ffb3d0ac0b11c544dbfd8cd5d806
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348557"
---
# <a name="-resource-visual-basic"></a>-Resource (Visual Basic)
Внедряет управляемый ресурс в сборку.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

или  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`filename`|Обязательно. Имя файла ресурсов, который необходимо внедрить в выходной файл. По умолчанию `filename` является общедоступной в сборке. Заключите имя файла в кавычки (""), если оно содержит пробел.|  
|`identifier`|Необязательный элемент. Логическое имя для ресурса; имя, используемое для его загрузки. По умолчанию используется имя файла. При необходимости можно указать, является ли ресурс открытым или закрытым в манифесте сборки, как показано ниже: `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>Примечания  
 Используйте `-linkresource`, чтобы связать ресурс со сборкой без помещения файла ресурсов в выходной файл.  
  
 Если `filename` является файлом ресурсов .NET Framework, который создается, например, программой [Resgen. exe (генератор файлов ресурсов)](../../../framework/tools/resgen-exe-resource-file-generator.md) или в среде разработки, доступ к нему можно получить с помощью членов пространства имен <xref:System.Resources> (Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager>). Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте один из следующих методов: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A>или <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 Краткой формой `-resource` является `-res`.  
  
 Сведения о том, как задать `-resource` в интегрированной среде разработки Visual Studio, см. в разделе [Управление ресурсами приложения (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `In.vb` и присоединяет `Rf.resource`файла ресурсов.  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)
- [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

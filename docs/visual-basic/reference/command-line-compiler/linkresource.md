---
title: -linkresource (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
ms.openlocfilehash: dee5384696d543442f3280b9fdb535a7d9b6f863
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005485"
---
# <a name="-linkresource-visual-basic"></a>-linkresource (Visual Basic)
Создает ссылку на управляемый ресурс.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-linkresource:filename[,identifier[,public|private]]  
```

или  

```console
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Обязательный. Файл ресурсов, связываемый с сборкой. Если имя файла содержит пробел, заключите его в кавычки ("").  
  
 `identifier`  
 Необязательный параметр. Логическое имя ресурса. Имя, используемое для загрузки ресурса. По умолчанию используется имя файла. При необходимости можно указать, является ли файл открытым или закрытым в манифесте сборки, например: `-linkres:filename.res,myname.res,public`. По умолчанию `filename` является общедоступным в сборке.  
  
## <a name="remarks"></a>Примечания  
 Параметр `-linkresource` не внедряет файл ресурсов в выходной файл; для этого используйте параметр `-resource`.  
  
 Для параметра `-linkresource` требуется один из параметров `-target`, кроме `-target:module`.  
  
 Если `filename` — это .NET Framework файл ресурсов, созданный, например, с помощью [Resgen. exe (генератор файлов ресурсов)](../../../framework/tools/resgen-exe-resource-file-generator.md) или в среде разработки, доступ к нему можно получить с помощью членов пространства имен <xref:System.Resources>. (Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager>.) Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте методы, которые начинаются с `GetManifestResource` в классе <xref:System.Reflection.Assembly>.  
  
 Имя файла может быть любым форматом файла. Например, может потребоваться сделать имеющуюся на компьютере библиотеку DLL частью сборки, поэтому ее можно разместить в глобальном кэше сборок и обеспечить к ней доступ из управляемого кода сборки.  
  
 Краткой формой `-linkresource` является `-linkres`.  
  
> [!NOTE]
> Параметр `-linkresource` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `in.vb` и ссылки на файл ресурсов `rf.resource`.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

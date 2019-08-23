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
ms.openlocfilehash: d92b0d08daf660880b648875c67c3b78069143d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69924863"
---
# <a name="-linkresource-visual-basic"></a>-linkresource (Visual Basic)
Создает ссылку на управляемый ресурс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-linkresource:filename[,identifier[,public|private]]  
' -or-  
-linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Обязательный. Файл ресурсов, связываемый с сборкой. Если имя файла содержит пробел, заключите его в кавычки ("").  
  
 `identifier`  
 Необязательный параметр. Логическое имя ресурса. Имя, используемое для загрузки ресурса. По умолчанию используется имя файла. При необходимости можно указать, является ли файл открытым или закрытым в манифесте сборки, например: `-linkres:filename.res,myname.res,public`. По умолчанию `filename` является общедоступным в сборке.  
  
## <a name="remarks"></a>Примечания  
 Параметр не внедряет файл ресурсов в выходной файл. для этого `-resource` используйте параметр. `-linkresource`  
  
 Для `-linkresource` параметра требуется один `-target` из параметров `-target:module`, кроме.  
  
 Если `filename` — это .NET Frameworkный файл ресурсов, например [Resgen. exe (генератор файлов ресурсов)](../../../framework/tools/resgen-exe-resource-file-generator.md) или в среде разработки, доступ к нему можно получить <xref:System.Resources> с помощью членов пространства имен. (Дополнительные сведения см. в разделе <xref:System.Resources.ResourceManager>.) Чтобы получить доступ ко всем остальным ресурсам во время выполнения, используйте методы, `GetManifestResource` начинающиеся <xref:System.Reflection.Assembly> с класса.  
  
 Имя файла может быть любым форматом файла. Например, может потребоваться сделать имеющуюся на компьютере библиотеку DLL частью сборки, поэтому ее можно разместить в глобальном кэше сборок и обеспечить к ней доступ из управляемого кода сборки.  
  
 Краткой формой `-linkresource` является `-linkres`.  
  
> [!NOTE]
> Этот `-linkresource` параметр недоступен в среде разработки Visual Studio. он доступен только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующий код компилирует `in.vb` и ссылается на файл `rf.resource`ресурсов.  
  
```console  
vbc -linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a>См. также

- [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md)
- [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

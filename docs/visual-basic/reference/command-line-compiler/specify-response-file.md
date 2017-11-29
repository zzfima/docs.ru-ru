---
title: "@ (указание файла ответа) (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: '@ (Specify Response File) compiler option [Visual Basic]'
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ced258713983ded06fa70cb65d56071b41cdc75b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-specify-response-file-visual-basic"></a>@ (указание файла ответа) (Visual Basic)
Указывает файл, содержащий параметры компилятора и файлы исходного кода для компиляции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
@response_file  
```  
  
## <a name="arguments"></a>Аргументы  
 `response_file`  
 Обязательный. Файл, содержащий параметры компилятора и файлы исходного кода для компиляции. Заключите имя файла в кавычки (» «), если он содержит пробелы.  
  
## <a name="remarks"></a>Примечания  
 Компилятор обрабатывает параметры компилятора и файлы исходного кода, указанного в файле ответов, как если бы они были указаны в командной строке.  
  
 Чтобы указать более одного файла ответов при компиляции, укажите несколько параметров файла ответов, следующие.  
  
```  
@file1.rsp @file2.rsp  
```  
  
 В ответ на несколько файлов, параметров компилятора и файлов исходного кода могут отображаться на одной строке. Каждый параметр компилятора должен записываться в одной строке (не может занимать несколько строк). Файл ответов можно включать комментарии, которые начинаются с `#` символов.  
  
 Можно комбинировать параметры, указанные в командной строке с параметрами, заданными в один или несколько файлов ответов. Компилятор обрабатывает параметры командной строки, они встречаются. Таким образом аргументы командной строки могут переопределять параметры, указанные в файле ответа. Таким же образом параметры в файле ответов переопределять ранее указанные параметры в командной строке или в других файлов ответов.  
  
 В Visual Basic предусмотрен файл Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe. Файл Vbc.rsp включается по умолчанию, если не `/noconfig` используется параметр. Дополнительные сведения см. в разделе [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).  
  
> [!NOTE]
>  `@` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.  
  
## <a name="example"></a>Пример  
 Следующие строки являются из образца файла ответов.  
  
```  
# build the first output file  
/target:exe   
/out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `@` параметр с именем файла ответов `File1.rsp`.  
  
```  
vbc @file1.rsp  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

---
title: "/keyfile (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/keyfile"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/keyfile compiler option [C#]"
  - "-keyfile compiler option [C#]"
  - "keyfile compiler option [C#]"
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /keyfile (C# Compiler Options)
Задает имя файла, содержащего ключ шифрования.  
  
## Синтаксис  
  
```  
/keyfile:file  
```  
  
## Аргументы  
  
|Термин|Определение|  
|------------|-----------------|  
|`file`|Имя файла, содержащего ключ строгого имени.|  
  
## Заметки  
 При использовании этого параметра компилятор вставляет открытый ключ из указанного файла в манифест сборки и затем подписывает окончательную сборку закрытым ключом.  Чтобы создать файл ключа, введите в командной строке sn \-k `file`.  
  
 При компиляции с параметром **\/target:module** имя файла ключа сохраняется в модуле и включается в сборку при компиляции с параметром [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Также можно передать сведения о шифровании компилятору с помощью параметра [\/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).  Если необходимо использовать частично подписанную сборку, применяйте параметр [\/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md).  
  
 Если для одной процедуры компиляции одновременно заданы параметры \/keyfile и \/keycontainer \(в командной строке или с помощью пользовательских атрибутов\), то сначала будет предпринята попытка использования контейнера ключей.  В случае успеха сборка подписывается данными контейнера ключей.  Если компилятор ключей не обнаружен, будет сделана попытка использовать файл, заданный параметром \/keyfile.  В случае успеха сборка подписывается данными из файла ключей, и эти данные о ключах будут установлены в контейнер ключей \(аналогично команде sn \-i\); таким образом, при следующей компиляции контейнер ключей будет действителен.  
  
 Обратите внимание, что файл ключей может содержать только открытый ключ.  
  
 Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) и [Отложенная подпись сборки](../Topic/Delay%20Signing%20an%20Assembly.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Подпись**.  
  
3.  Измените свойство **Выберите файл ключей строгого имени**.  
  
 Программный доступ к этому параметру компилятора возможен с помощью свойства <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
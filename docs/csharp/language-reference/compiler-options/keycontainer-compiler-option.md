---
title: "/keycontainer (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/keycontainer"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/keycontainer compiler option [C#]"
  - "keycontainer compiler option [C#]"
  - "-keycontainer compiler option [C#]"
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# /keycontainer (C# Compiler Options)
Задает имя контейнера криптографического ключа.  
  
## Синтаксис  
  
```  
/keycontainer:string  
```  
  
## Аргументы  
 `string`  
 Строгое имя контейнера ключа.  
  
## Заметки  
 При использовании параметра **\/keycontainer** компилятор создает компонент, который можно сделать общим, вставляя в манифест сборки открытый ключ из указанного контейнера и подписывая окончательную сборку закрытым ключом.  Для создания файла ключа введите sn \-k `file` в командной строке. sn \-i установит пару ключей в контейнер.  
  
 При компиляции с параметром [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) имя файла ключа сохраняется в модуле и включается в сборку при компиляции этого модуля с параметром [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Этот параметр также можно задать в качестве настраиваемого атрибута \(<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>\) в исходном коде любого модуля языка MSIL.  
  
 Сведения о шифровании можно передать компилятору также с помощью параметра [\/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md).  Если необходимо добавить в манифест сборки открытый ключ, но отложить подпись сборки до завершения ее тестирования, используйте параметр [\/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md).  
  
 Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) и [Отложенная подпись сборки](../Topic/Delay%20Signing%20an%20Assembly.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Данный параметр компилятора недоступен в среде разработки Visual Studio.  
  
 Программный доступ к этому параметру компилятора возможен с помощью свойства <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
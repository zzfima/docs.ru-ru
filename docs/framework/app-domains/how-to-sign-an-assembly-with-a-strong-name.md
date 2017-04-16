---
title: "Практическое руководство. Подписание сборки строгим именем | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "сборки [платформа .NET Framework], подписывание"
  - "сборки [платформа .NET Framework], строгие имена"
  - "подписывание сборок"
  - "сборки со строгими именами, подписывание с использованием строгих имен"
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
caps.latest.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 23
---
# Практическое руководство. Подписание сборки строгим именем
Существует несколько способов подписать сборку строгим именем:  
  
-   С использованием **Подписывание** в диалоговом окне **Свойства** проекта в Visual Studio. Это самый простой и удобный способ подписать сборку строгим именем.  
  
-   С использованием [компоновщика сборок \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md), который связывает модуль кода .NET Framework \(NETMODULE\-файл\) с файлом ключа.  
  
-   С использованием атрибутов сборки, позволяющих вставить в код данные строгого имени. Можно использовать либо <xref:System.Reflection.AssemblyKeyFileAttribute>, либо <xref:System.Reflection.AssemblyKeyNameAttribute> в зависимости от того, где находится используемый файл ключа.  
  
-   С использованием параметров компилятора.  
  
 Для подписи сборки строгим именем необходимо иметь пару ключей шифрования. Дополнительные сведения о создании пары ключей см. в разделе [Практическое руководство. Создание пары открытого и закрытого ключей](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).  
  
### Создание и подпись сборки строгим именем с помощью Visual Studio  
  
1.  В **обозревателе решений** откройте контекстное меню проекта и выберите **Свойства**.  
  
2.  Перейдите на вкладку **Подписывание**.  
  
3.  Выберите поле **Подписать сборку**.  
  
4.  В поле **Выберите файл ключей строгого имени** нажмите **\<Обзор…\>**, после чего выберите файл ключей. Чтобы создать новый файл ключей, выберите **\<Создать…\>** и введите его имя в диалоговом окне **Создание ключа строгого имени**.  
  
### Создание и подпись сборки строгим именем с помощью компоновщика сборок  
  
-   В [командной строке Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md) введите следующую команду:  
  
     **al** **\/out:**\<*имя\_сборки*\> *\<имя\_модуля\>* **\/keyfile:**\<*имя\_файла*\>  
  
     Здесь:  
  
     *assemblyName*  
     Имя строго подписанной сборки \(файл DLL или EXE\), которая будет создана компоновщиком сборок.  
  
     *имя модуля*  
     Имя модуля кода .NET Framework \(NETMODULE\-файла\), который содержит один тип или несколько. NETMODULE\-файл можно создать путем компиляции кода с параметром `/target:module` в C\# или Visual Basic.  
  
     *имя файла*  
     Имя контейнера или файла, содержащего пару ключей. Компоновщик сборок интерпретирует относительный путь с точки зрения текущего каталога.  
  
 Следующий пример подписывает сборку `MyAssembly.dll` строгим именем с помощью файла ключей `sgKey.snk`.  
  
```  
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
 Дополнительные сведения об использовании этого инструмента см. в разделе [Компоновщик сборок](../../../docs/framework/tools/al-exe-assembly-linker.md).  
  
#### Подпись сборки строгим именем с помощью атрибутов  
  
1.  Добавьте <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=fullName> или <xref:System.Reflection.AssemblyKeyNameAttribute> в файл исходного кода и укажите имя файла или контейнера, содержащего пару ключей, которая используется при подписи сборки строгим именем.  
  
2.  Компилируйте файл исходного кода в обычном режиме.  
  
> [!NOTE]
>  Компиляторы C\# и Visual Basic выдают предупреждения \(CS1699 и BC41008, соответственно\), если в исходном коде встречается <xref:System.Reflection.AssemblyKeyFileAttribute> или <xref:System.Reflection.AssemblyKeyNameAttribute>. Эти предупреждения можно игнорировать.  
  
 В следующем примере кода используется атрибут <xref:System.Reflection.AssemblyKeyFileAttribute> с файлом ключей под названием `keyfile.snk`, который находится в том же каталоге, где компилируется сборка.  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
 Кроме того, при компиляции исходного файла можно использовать отложенную подпись. Дополнительные сведения см. в разделе [Отложенная подпись сборки](../../../docs/framework/app-domains/delay-sign-assembly.md).  
  
### Подпись сборки строгим именем с использованием компилятора  
  
-   Компилируйте файлы исходного кода с помощью параметра компилятора `/keyfile` или `/delaysign` в C\# и Visual Basic либо параметра компоновщика `/KEYFILE` или `/DELAYSIGN` в C\+\+. После имени параметра добавьте двоеточие и имя файла ключей. При использовании компиляторов, работающих в режиме командной строки, можно скопировать файл ключей в каталог, содержащий файлы исходного кода.  
  
     Подробные сведения об отложенной подписи см. в разделе [Отложенная подпись сборки](../../../docs/framework/app-domains/delay-sign-assembly.md).  
  
     В следующем примере используется компилятор C\# и сборка `UtilityLibrary.dll` подписывается строгим именем с помощью файла ключей `sgKey.snk`.  
  
    ```  
    csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
    ```  
  
## См. также  
 [Создание и использование сборок со строгими именами](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)   
 [Практическое руководство. Создание пары открытого и закрытого ключей](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)   
 [Al.exe \(компоновщик сборок\)](../../../docs/framework/tools/al-exe-assembly-linker.md)   
 [Отложенная подпись сборки](../../../docs/framework/app-domains/delay-sign-assembly.md)   
 [Управление сборками и подписывание манифестов](../Topic/Managing%20Assembly%20and%20Manifest%20Signing.md)   
 [Страница "Подписывание" в конструкторе проектов](../Topic/Signing%20Page,%20Project%20Designer.md)
---
title: "Практическое руководство. Создание ссылки на сборку со строгим именем"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5934f67387e29bfbd4f011ad2ba47f50d81b983
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-reference-a-strong-named-assembly"></a>Практическое руководство. Создание ссылки на сборку со строгим именем
Процесс использования ссылок на типы или ресурсы, находящиеся в сборке со строгим именем, обычно понятен. Создать ссылку можно в момент компиляции (ранняя привязка) или же во время выполнения.  
  
 Во время компиляции создание ссылки происходит, когда компилятору указывается, что текущая сборка явно ссылается на другую сборку. При создании ссылок в момент компиляции компилятор автоматически получает открытый ключ нужной сборки со строгим именем и помещает его в ссылку компилируемой сборки.  
  
> [!NOTE]
>  Сборка со строгими именами может использовать только типы из других сборок со строгими именами. В противном случае нарушается безопасность сборки со строгими именами.  
  
### <a name="to-make-a-compile-time-reference-to-a-strong-named-assembly"></a>Создание ссылки на сборку со строгим именем во время компиляции  
  
1.  В командной строке введите следующую команду:  
  
     \<*команда компилятора*> **/reference:**\<*имя сборки*>  
  
     В этой команде *команда компилятора* — команда компилятора для используемого языка, а *имя сборки* — строгое имя сборки, на которую создается ссылка. Кроме того, для создания сборки библиотеки можно использовать другие параметры компилятора, такие как **/t:library**.  
  
 В следующем примере показано создание сборки с именем `myAssembly.dll`, ссылается на сборку со строгим именем `myLibAssembly.dll` из модуля кода с именем `myAssembly.cs`.  
  
```  
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  
  
### <a name="to-make-a-run-time-reference-to-a-strong-named-assembly"></a>Создание ссылки на сборку со строгим именем во время выполнения  
  
1.  Если вы создаете ссылку на сборку со строгим именем во время выполнения (например, с помощью метода <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> или <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>), необходимо использовать отображаемое имя сборки со строгим именем, на которую указывает ссылка. Отображаемое имя имеет следующий синтаксис:  
  
     \<*имя сборки*>**,** \<*номер версии*>**,** \<*язык и региональные параметры*>**,** \<*маркер открытого ключа*>  
  
     Пример:  
  
    ```  
    myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33   
    ```  
  
     В этом примере `PublicKeyToken` представляет собой шестнадцатеричную форму маркера открытого ключа. Если значение языка и региональных параметров отсутствует, используйте `Culture=neutral`.  
  
 В следующем примере кода показано использование этих данных с помощью метода <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.  
  
 [!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)]
 [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)]
 [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]  
  
 Распечатать в шестнадцатеричном формате открытый ключ и токен открытого ключа для определенной сборки можно с помощью следующей команды [строгого имени (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md):  
  
 **sn -Tp \<** *сборка* **>**  
  
 Если же имеется файл открытого ключа, то вместо этого можно использовать следующую команду (обратите внимание на разный регистр символов в параметре командной строки):  
  
 **sn -tp \<** *сборка* **>**  
  
## <a name="see-also"></a>См. также  
 [Создание и использование сборок со строгими именами](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)

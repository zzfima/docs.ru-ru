---
title: "Практическое руководство. Создание политики издателя | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "GAC - глобальный кэш сборок, сборка политики издателя"
  - "глобальный кэш сборок, сборка политики издателя"
  - "сборка политики издателя"
  - "файлы политики издателя"
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Практическое руководство. Создание политики издателя
Поставщики сборок могут сделать обязательным использование приложениями более новой версии какой\-либо сборки путем включения файла политики издателя с обновленной сборкой.  Файл политики издателя задает перенаправление сборок и параметры базы кода, он использует тот же формат, что и файл конфигурации приложения.  Файл политики издателя компилируется в сборку и помещается в глобальный кэш сборок.  
  
 Создание политики издателя происходит в три этапа.  
  
1.  Создание файла политики издателя.  
  
2.  Создание сборки политики издателя.  
  
3.  Добавление сборки политики издателя в глобальный кэш сборок.  
  
 Схема для политики издателя описана в разделе [Перенаправление версий сборок](../../../docs/framework/configure-apps/redirect-assembly-versions.md).  В следующем примере показан файл политики издателя, перенаправляющий одну версию сборки `myAssembly` на другую.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->  
         <bindingRedirect oldVersion="1.0.0.0"  
                          newVersion="2.0.0.0"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Способы задания базы кода см. в разделе [Указание расположения сборки](../../../docs/framework/configure-apps/specify-assembly-location.md).  
  
## Создание сборки политики издателя  
 Для создания сборки политики издателя следует использовать [Компоновщик сборок \(Al.exe\)](../../../docs/framework/tools/al-exe-assembly-linker.md).  
  
#### Чтобы создать сборку политики издателя  
  
1.  Введите следующую команду в командной строке:  
  
     **al \/link:** *publisherPolicyFile* **\/out:** *publisherPolicyAssemblyFile* **\/keyfile:** *keyPairFile* **\/platform:** *processorArchitecture*  
  
     В этой команде указаны следующие данные:  
  
    -   Аргумент *publisherPolicyFile* является именем файла политики издателя.  
  
    -   Аргумент *publisherPolicyAssemblyFile* — имя сборки политики издателя, которая является результатом выполнения этой команды.  Имя файла сборки должно иметь формат:  
  
         **policy.** *majorNumber* **.** *minorNumber* **.** *mainAssemblyName* **.dll**  
  
    -   Аргумент *keyPairFile* — имя файла, содержащего пару ключей.  Сборку и сборку политики издателя необходимо подписывать одной и той же парой ключей.  
  
    -   Аргумент *processorArchitecture* указывает целевую платформу для специфической для процессора сборки.  
  
        > [!NOTE]
        >  Возможности указывать целевую архитектуру процессора не существовало до .NET Framework версии 2.0.  
  
     Следующая команда создает сборку политики издателя `policy.1.0.myAssembly` из файла политики издателя `pub.config`, назначает строгое имя сборки с помощью пары ключей в файле `sgKey.snk`, а также указывает, что целевой архитектурой процессора является x86.  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     Сборка политики издателя должна соответствовать архитектуре процессора сборки, к которой она применяется.  Поэтому если установлено значение <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> для <xref:System.Reflection.ProcessorArchitecture> сборки, сборка политики издателя для этой сборки должна создаваться с помощью `/platform:anycpu`.  Необходимо предоставить отдельную сборку политики издателя для каждой специфической для процессора сборки.  
  
     Из этого следует, что для изменения архитектуры процессора для сборки необходимо изменить номер компонентов основной и добавочной версии, чтобы для новой сборки политики издателя была доступна правильная архитектура процессора.  Старая сборка политики издателя не может применяться к сборке, если она имеет отличную архитектуру процессора.  
  
     Еще одним следствием является то, что нельзя использовать компоновщик версии 2.0 для создания сборки политики издателя для сборки, созданной с помощью более ранней версии .NET Framework, поскольку он всегда указывает архитектуру процессора.  
  
## Добавление сборки политики издателя в глобальный кэш сборок  
 Чтобы добавить сборку в глобальный кэш сборок, используйте [средство глобального кэша сборок \(Gacutil.exe\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).  
  
#### Чтобы добавить сборку политики издателя в глобальный кэш сборок  
  
1.  Введите следующую команду в командной строке:  
  
     **gacutil \/i**  *publisherPolicyAssemblyFile*  
  
     Следующая команда добавляет `policy.1.0.myAssembly.dll` в глобальный кэш сборок.  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  Сборка политики издателя может быть добавлена в глобальный кэш сборок, только если исходный файл политики издателя расположен в том же каталоге, что и сборка.  
  
## См. также  
 [Программирование с использованием сборок](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Настройка приложений](../../../docs/framework/configure-apps/index.md)   
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/ru-ru/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)   
 [Схема параметров среды выполнения](../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md)   
 [Перенаправление версий сборки](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
---
title: Практическое руководство. Создание политики издателя
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 91971e4d41c3a54fa72ae73a3655dab650019676
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-create-a-publisher-policy"></a>Практическое руководство. Создание политики издателя
Поставщики сборок можно указать, что приложений следует использовать более новой версии сборки, включая файл политики издателя с обновленной сборкой. Файл политики издателя задает перенаправление сборки и параметры базового каталога кода и используется тот же формат в файле конфигурации приложения. Файл политики издателя компилируется в сборку и помещен в глобальном кэше сборок.  
  
 Существует три действия, связанные с созданием политики издателя:  
  
1.  Создайте файл политики издателя.  
  
2.  Создайте сборка политики издателя.  
  
3.  Добавьте сборку в глобальном кэше сборок.  
  
 Схема для политики издателя описана в [Перенаправление версий сборок](../../../docs/framework/configure-apps/redirect-assembly-versions.md). В следующем примере показано издателя файла политики, который перенаправляет одну версию `myAssembly` в другой.  
  
```xml  
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
  
 Дополнительные сведения о задания базы кода см. в разделе [Указание расположения сборки](../../../docs/framework/configure-apps/specify-assembly-location.md).  
  
## <a name="creating-the-publisher-policy-assembly"></a>Создание сборка политики издателя  
 Используйте [компоновщик сборок (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) Создание сборка политики издателя.  
  
#### <a name="to-create-a-publisher-policy-assembly"></a>Чтобы создать сборка политики издателя  
  
1.  В командной строке введите следующую команду:  
  
     **/ LINK AL:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:**  *keyPairFile* **/Platform:** *processorArchitecture*  
  
     В этой команде:  
  
    -   *PublisherPolicyFile* аргумент — имя файла политики издателя.  
  
    -   *PublisherPolicyAssemblyFile* аргумент является именем сборка политики издателя, полученный в результате этой команды. Имя файла сборки должно иметь формат:  
  
         **Политика.** *majorNumber* **.** *minorNumber* **.** *mainAssemblyName* **.dll**  
  
    -   *KeyPairFile* аргумент — имя файла, содержащего пару ключей. Необходимо подписать сборку и сборка политики издателя с ту же пару ключей.  
  
    -   *ProcessorArchitecture* аргумент указывает платформы, специфический для процессора сборки.  
  
        > [!NOTE]
        >  Возможности указывать целевую архитектуру процессора впервые появился в платформе .NET Framework версии 2.0.  
  
     Следующая команда создает сборку политики издателя `policy.1.0.myAssembly` из файла политики издателя с именем `pub.config`, назначает строгое имя сборки с помощью пары ключей из `sgKey.snk` файла и указывает, что целевой x86 архитектура процессора.  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     Сборка политики издателя должна соответствовать архитектуре процессора сборки, которая применяется к. Таким образом Если сборка имеет <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> значение <xref:System.Reflection.ProcessorArchitecture.MSIL>, сборка политики издателя для этой сборки, которые должны создаваться с помощью `/platform:anycpu`. Необходимо предоставить отдельную сборку для каждой сборки для конкретного процессора.  
  
     Вследствие этого правила является, чтобы изменить архитектуру процессора для сборки, необходимо изменить основной или дополнительный компонент номера версии, поэтому можно указать новый сборка политики издателя с правильную архитектуру процессора. Старая сборка политики издателя не может применяться к сборке, если она имеет отличную архитектуру процессора.  
  
     Второе — что компоновщик версии 2.0 не может использоваться для создания сборка политики издателя для компиляции с помощью более ранних версий платформы .NET Framework, поскольку он всегда указывает архитектуру процессора сборки.  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Добавление сборка политики издателя в глобальный кэш сборок  
 Используйте [средство глобального кэша сборок (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) Добавление сборка политики издателя в глобальный кэш сборок.  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Чтобы добавить сборку в глобальный кэш сборок  
  
1.  В командной строке введите следующую команду:  
  
     **Gacutil /i***publisherPolicyAssemblyFile*   
  
     Следующая команда добавляет `policy.1.0.myAssembly.dll` в глобальном кэше сборок.  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  Сборка политики издателя не добавить в глобальный кэш сборок, если исходный файл политики издателя расположен в том же каталоге, что и сборка.  
  
## <a name="see-also"></a>См. также  
 [Программирование с использованием сборок](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Настройка приложений](../../../docs/framework/configure-apps/index.md)  
 [Настройка приложений .NET Framework](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [Схема параметров среды выполнения](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md)  
 [Перенаправление версий сборки](../../../docs/framework/configure-apps/redirect-assembly-versions.md)

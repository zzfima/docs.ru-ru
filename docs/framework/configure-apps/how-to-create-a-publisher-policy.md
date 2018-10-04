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
ms.openlocfilehash: e7cac3c7e6c588a82e9dfff169ba7b7aa72c35f8
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48793296"
---
# <a name="how-to-create-a-publisher-policy"></a>Практическое руководство. Создание политики издателя
Поставщики сборок можно указать, что приложения должны использовать более новой версии сборки, включая файл политики издателя с обновленной сборкой. Файл политики издателя указывает перенаправление сборки и параметры базы кода и используется тот же формат, что и файл конфигурации приложения. Файл политики издателя компилируется в сборку и помещен в глобальном кэше сборок.  
  
 Существует три действия, связанные с созданием политики издателя:  
  
1.  Создайте файл политики издателя.  
  
2.  Создание сборки политики издателя.  
  
3.  Добавьте сборку в глобальный кэш сборок.  
  
 Схема для политики издателя описана в [Перенаправление версий сборки](../../../docs/framework/configure-apps/redirect-assembly-versions.md). В следующем примере показано издателя файл политики, который перенаправляет одну версию `myAssembly` в другой.  
  
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
  
 Чтобы узнать, как для указания базового кода, см. в разделе [Указание расположения сборки](../../../docs/framework/configure-apps/specify-assembly-location.md).  
  
## <a name="creating-the-publisher-policy-assembly"></a>Создание сборки политики издателя  
 Используйте [компоновщик сборок (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) для создания сборки политики издателя.  
  
#### <a name="to-create-a-publisher-policy-assembly"></a>Для создания сборки политики издателя  
  
1.  Введите следующую команду в командной строке:  
  
     **Al/LINK:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:**  *keyPairFile* **/Platform:** *processorArchitecture*  
  
     В этой команде:  
  
    -   *PublisherPolicyFile* аргумента — имя файла политики издателя.  
  
    -   *PublisherPolicyAssemblyFile* аргумента — имя сборки политики издателя, полученный в результате этой команды. Имя файла сборки должны иметь формат:  
  
         **политика.** *majorNumber* **.** *minorNumber* **.** *mainAssemblyName* **.dll**  
  
    -   *KeyPairFile* аргумента — имя файла, содержащего пару ключей. Необходимо подписать сборку и сборки политики издателя ту же пару ключей.  
  
    -   *ProcessorArchitecture* аргумент определяет платформы, являющейся целевой для сборки с конкретного процессора.  
  
        > [!NOTE]
        >  Возможность использования на архитектуру процессора является новым в .NET Framework версии 2.0.  
  
     Следующая команда создает сборку политики издателя `policy.1.0.myAssembly` из файла политики издателя с именем `pub.config`, назначает строгое имя сборки с помощью пары ключей в `sgKey.snk` файла и указывает, что целевой x86 архитектура процессора.  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     Сборка политики издателя должен соответствовать архитектуре процессора сборки, к которому он применяется. Таким образом Если сборка имеет <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> значение <xref:System.Reflection.ProcessorArchitecture.MSIL>, сборка политики издателя для этой сборки, которые должны создаваться с помощью `/platform:anycpu`. Необходимо предоставить отдельную сборку политики издателя для каждой сборки для конкретного процессора.  
  
     Вследствие этого правила является, чтобы изменить архитектуру процессора для сборки, необходимо изменить основной или вспомогательной компонент номера версии, таким образом, можно указать новую сборку политики издателя с правильную архитектуру процессора. Старая сборка политики издателя не может применяться к сборке, если она имеет архитектуру процессора, отличной от.  
  
     Второе — то, что компоновщик версии 2.0 не может использоваться для создания сборки политики издателя для сборки, скомпилированной с помощью более ранних версий платформы .NET Framework, поскольку он всегда задает архитектуру процессора.  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Добавление сборки политики издателя в глобальный кэш сборок  
 Используйте [средство глобального кэша сборок (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) добавляемый сборку в глобальный кэш сборок.  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a>Чтобы добавить сборку в глобальный кэш сборок  
  
1.  Введите следующую команду в командной строке:  
  
     **Gacutil /i***publisherPolicyAssemblyFile*  
  
     Следующая команда добавляет `policy.1.0.myAssembly.dll` в глобальном кэше сборок.  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  Сборку в глобальный кэш сборок невозможно, если исходный файл политики издателя находится в том же каталоге, что и сборка.  
  
## <a name="see-also"></a>См. также  
 [Программирование с использованием сборок](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Настройка приложений](../../../docs/framework/configure-apps/index.md)  
 [Настройка приложений .NET Framework](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [Схема параметров среды выполнения](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../docs/framework/configure-apps/file-schema/index.md)  
 [Перенаправление версий сборки](../../../docs/framework/configure-apps/redirect-assembly-versions.md)

---
title: "Практическое руководство. Отключение функции пропуска строгих имен"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, loading into trusted application domains
ms.assetid: 234e088c-3b11-495a-8817-e0962be79d82
caps.latest.revision: 30
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0af565c6d27be6a5a22bfb0fd1f90e4e46deec33
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-disable-the-strong-name-bypass-feature"></a>Практическое руководство. Отключение функции пропуска строгих имен
Начиная с версии .NET Framework 3.5 с пакетом обновления 1 (SP1), подписи строгого имени не проходили проверку при загрузке сборки в объект <xref:System.AppDomain> с полным доверием, например в `MyComputer` по умолчанию для зоны <xref:System.AppDomain>. Это называется возможностью обхода строгих имен. В среде с полным доверием всегда успешно обрабатываются запросы <xref:System.Security.Permissions.StrongNameIdentityPermission> для подписанных сборок с полным доверием независимо от их подписи. Единственное исключение связано с тем, что сборка должна иметь полное доверие, потому что полное доверие имеет ее зона. Так как в этом случае наличие строгого имени не является решающим фактором, смысла в проверке подписи нет. Пропуск проверки подписей строгого имени позволяет значительно повысить производительность приложения.  
  
 Функция пропуска применяется ко всем сборкам с полным доверием, если у них нет отложенных подписей и они загружены в любой домен <xref:System.AppDomain> с полным доверием из каталога, заданным свойством <xref:System.AppDomainSetup.ApplicationBase%2A>.  
  
 Можно отключить пропуск для всех приложений на компьютере, если изменить значение параметра реестра. Для отключения пропуска для отдельного приложения необходимо внести соответствующие изменения в файл конфигурации приложения. Если функция пропуска строгих имен отключена в реестре, ее невозможно включить для отдельного приложения.  
  
 При отключении функции пропуска строгие имена проверяются только на правильность; наличие разрешения <xref:System.Security.Permissions.StrongNameIdentityPermission> не проверяется. Если требуется подтвердить то или иное строгое имя, такую проверку необходимо выполнять отдельно.  
  
> [!IMPORTANT]
>  Возможность принудительного проведения проверки строгого имени зависит от значения параметра реестра, как описано ниже. Если приложение выполняется от имени учетной записи, для которой в списке управления доступом не выделено разрешение на доступ к этому параметру реестра, проведение проверки невозможно. Необходимо настроить права ACL для данного раздела так, чтобы к нему могла получить доступ любая сборка.  
  
### <a name="to-disable-the-strong-name-bypass-feature-for-all-applications"></a>Отключение функции обхода строгих имен для всех приложений  
  
-   На 32-разрядных компьютерах в разделе HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework системного реестра создайте запись DWORD со значением 0 и именем `AllowStrongNameBypass`.  
  
-   На 64-разрядных компьютерах в разделах системного реестра HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework и HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework создать запись типа DWORD со значением 0 с именем `AllowStrongNameBypass`.  
  
### <a name="to-disable-the-strong-name-bypass-feature-for-a-single-application"></a>Отключение функции обхода строгих имен для отдельного приложения  
  
1.  Откройте или создайте файл конфигурации приложения.  
  
     Дополнительные сведения об этом файле см. в разделе "Файлы конфигурации приложений" документа [Настройка приложений](../../../docs/framework/configure-apps/index.md).  
  
2.  Добавьте следующую запись:  
  
    ```xml  
    <configuration>  
      <runtime>  
        <bypassTrustedAppStrongNames enabled="false" />  
      </runtime>  
    </configuration>  
    ```  
  
 Функцию пропуска строгих имен для приложения можно снова включить, удалив соответствующий элемент из файла конфигурации или установив для атрибута значение "true".  
  
> [!NOTE]
>  Функцию проверки строгих имен можно включать и отключать на уровне приложения, если пропуск строгих имен включен на уровне компьютера. Если функция пропуска на уровне компьютера отключена, строгие имена будут проверяться для всех приложений и пропустить проверку для отдельного приложения будет невозможно.  
  
## <a name="see-also"></a>См. также  
 [Sn.exe (средство строгих имен)](../../../docs/framework/tools/sn-exe-strong-name-tool.md)   
 [Элемент \<bypassTrustedAppStrongNames>t](../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)   
 [Создание и использование сборок со строгими именами](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)


---
title: "Средство регистрации ServiceModel (ServiceModelReg.exe) | Microsoft Docs"
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
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 26
---
# Средство регистрации ServiceModel (ServiceModelReg.exe)
Этот инструмент командной строки предоставляет возможность управления регистрацией WCF и компонентов WF на одном компьютере.Обычно вам не требуется использовать данное средство, так как при установке компонентов WCF и WF производится их правильная настройка.Но если вы испытываете проблемы с активацией службы, то вы можете попробовать зарегистрировать компоненты с помощью этого средства.  
  
## Синтаксис  
  
```  
  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## Заметки  
 Это средство можно найти в следующей папке:  
  
 %SystemRoot%\\Microsoft.Net\\Framework\\v3.0\\Windows Communication Foundation\\  
  
> [!NOTE]
>  При запуске средства регистрации ServiceModel в [!INCLUDE[wv](../../../includes/wv-md.md)] в диалоговом окне **Компоненты Windows** может отсутствовать информация о том, что параметр **Активация Windows Communication Foundation по HTTP** в разделе **Microsoft .NET Framework 3.0** включен.Для доступа к диалоговому окну **Компоненты Windows** необходимо нажать кнопку **Пуск**, выбрать **Выполнить** и ввести **OptionalFeatures**.  
  
 В следующей таблице представлены параметры, которые могут использоваться с ServiceModelReg.exe.  
  
|Параметр|Описание|  
|--------------|--------------|  
|`-ia`|Устанавливает все компоненты WCF и WF.|  
|`-ua`|Удаляет все компоненты WCF и WF.|  
|`-r`|Ремонтирует все компоненты WCF и WF.|  
|`-i`|Устанавливает компоненты WCF и WF, заданные с помощью ключа «\-с».|  
|`-u`|Удаляет компоненты WCF и WF, заданные с помощью ключа «\-с».|  
|`-c`|Устанавливает или удаляет компонент.<br /><br /> -   httpnamespace — резервирование пространства имен HTTP<br />-   tcpportsharing — совместное использование TCP\-порта<br />-   tcpactivation — служба активации TCP \(не поддерживается в .NET 4 Client Profile\)<br />-   namedpipeactivation — служба активации именованных каналов \(не поддерживается в .NET 4 Client Profile\)<br />-   tcpactivation — служба активации MSMQ \(не поддерживается в .NET 4 Client Profile\)<br />-   etw — манифесты трассировки событий Windows \(Windows Vista и более поздних версий\)|  
|`-q`|Тихий режим \(только для отображения журнала ошибок\)|  
|`-v`|Режим подробного вывода.|  
|`-nologo`|Подавляет вывод логотипа и баннера об авторском праве.|  
|`-?`|Отображает текст справки.|  
  
## Исправление ошибки FileLoadException  
 Если на компьютере устанавливались предыдущие версии [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], при запуске средства ServiceModelReg для регистрации новой версии может возникнуть ошибка `FileLoadFoundException`.Это может произойти, даже если пользователь вручную удалил файлы из каталога установки предыдущей версии, но оставил файл machine.config без изменений.  
  
 Сообщение об ошибке подобно приведенному ниже.  
  
```  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 Из этого сообщения об ошибке можно выяснить, что сборка System.ServiceModel версии 2.0.0.0 была установлена более ранней CTP\-версией.Текущая версия сборки System.ServiceModel — 3.0.0.0.Таким образом, данная проблема возникает при попытке установить официальную версию [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] на компьютер, где CTP\-версия [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] была установлена, но не полностью удалена.  
  
 ServiceModelReg.exe не может удалять записи предыдущих версий или регистрировать записи новой версии.Единственным решением является изменение файла machine.config вручную.Этот файл находится в следующем расположении.  
  
```  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config   
```  
  
 В случае использования [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] на 64\-разрядном компьютере также необходимо отредактировать одноименный файл. Путь к этому файлу указан ниже.  
  
```  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config   
```  
  
 Найдите в этом файле все XML\-узлы, относящиеся к "System.ServiceModel, Version\=2.0.0.0", затем удалите эти узлы и все их дочерние узлы.Сохраните файл и повторно запустите ServiceModelReg.exe. Проблема устранена.  
  
## Примеры  
 В следующих примерах показано, как использовать наиболее употребимые параметры средства ServiceModelReg.exe.  
  
```  
ServiceModelReg.exe -ia  
  Installs all components  
ServiceModelReg.exe -i -c:httpnamespace -c:etw  
  Installs HTTP namespace reservation and ETW manifests  
ServiceModelReg.exe -u -c:etw  
  Uninstalls ETW manifests  
ServiceModelReg.exe -r  
  Repairs an extended install  
```
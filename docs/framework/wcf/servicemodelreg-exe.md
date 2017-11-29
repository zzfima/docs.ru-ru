---
title: "Средство регистрации ServiceModel (ServiceModelReg.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7032fd6005d5eccf27e0ca34cd89c050260d6e4b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a>Средство регистрации ServiceModel (ServiceModelReg.exe)
Этот инструмент командной строки предоставляет возможность управления регистрацией компонентов WCF и WF на одном компьютере. В обычных условиях использование данного средства не требуется, так как при установке компонентов WCF и WF производится их правильная настройка. Но если вы испытываете проблемы с активацией службы, то можно попробовать зарегистрировать компоненты с помощью этого средства.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a>Примечания  
 Это средство можно найти в следующей папке:  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\  
  
> [!NOTE]
>  При запуске средства регистрации ServiceModel в [!INCLUDE[wv](../../../includes/wv-md.md)], **компоненты Windows** диалоговое окно может не отражать, **активация Windows Communication Foundation HTTP** параметра в разделе **Microsoft .NET Framework 3.0** включен. **Компоненты Windows** диалогового окна можно получить, щелкнув **запустить**, нажмите кнопку **запуска** и введя **OptionalFeatures**.  
  
 В следующей таблице представлены параметры, которые могут использоваться с ServiceModelReg.exe.  
  
|Параметр|Описание|  
|------------|-----------------|  
|`-ia`|Устанавливает все компоненты WCF и WF.|  
|`-ua`|Удаляет все компоненты WCF и WF.|  
|`-r`|Ремонтирует все компоненты WCF и WF.|  
|`-i`|Устанавливает компоненты WCF и WF, заданные с помощью ключа «-с».|  
|`-u`|Удаляет компоненты WCF и WF, заданные с помощью ключа «-с».|  
|`-c`|Устанавливает или удаляет компонент.<br /><br /> -httpnamespace резервирование пространства имен HTTP<br />Служба совместного использования портов - tcpportsharing TCP<br />Служба активации - tcpactivation TCP (не поддерживается в .NET 4 Client Profile)<br />Служба - namedpipeactivation-активации именованных каналов (не поддерживается в .NET 4 Client Profile<br />Служба активации - msmqactivation-MSMQ (не поддерживается в .NET 4 Client Profile<br />манифесты трассировки событий ETW - трассировка событий Windows — (Windows Vista или более поздней версии)|  
|`-q`|Тихий режим (только для отображения журнала ошибок)|  
|`-v`|Режим подробного вывода.|  
|`-nologo`|Подавляет вывод логотипа и сообщения об авторском праве.|  
|`-?`|Отображает текст справки|  
  
## <a name="fixing-the-fileloadexception-error"></a>Исправление ошибки FileLoadException  
 Если на компьютере устанавливались предыдущие версии [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], при запуске средства ServiceModelReg для регистрации новой версии может возникнуть ошибка `FileLoadFoundException`. Это может произойти, даже если пользователь вручную удалил файлы из каталога установки предыдущей версии, но оставил файл machine.config без изменений.  
  
 Сообщение об ошибке подобно приведенному ниже.  
  
```  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 Из этого сообщения об ошибке можно выяснить, что сборка System.ServiceModel версии 2.0.0.0 была установлена более ранней CTP-версией. Текущая версия сборки System.ServiceModel - 3.0.0.0. Таким образом, данная проблема возникает при попытке установить официальную версию [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] на компьютер, где CTP-версия [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] была установлена, но не полностью удалена.  
  
 ServiceModelReg.exe не может удалять записи предыдущих версий или регистрировать записи новой версии. Единственным решением является изменение файла machine.config вручную. Этот файл находится в следующем расположении.  
  
```  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config   
```  
  
 В случае использования [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] на 64-разрядном компьютере также необходимо отредактировать одноименный файл. Путь к этому файлу указан ниже.  
  
```  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config   
```  
  
 Найдите все XML-узлы в этом файле, на которое ссылается на «System.ServiceModel, Version = 2.0.0.0», удалите их и все дочерние узлы. Сохраните файл и повторно запустите ServiceModelReg.exe. Проблема устранена.  
  
## <a name="examples"></a>Примеры  
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

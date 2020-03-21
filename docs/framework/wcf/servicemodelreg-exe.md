---
title: Средство регистрации ServiceModel (ServiceModelReg.exe)
ms.date: 03/30/2017
ms.assetid: 396ec5ae-e34f-4c64-a164-fcf50e86b6ac
ms.openlocfilehash: a6f65ccc6caa0a7e496e7de8c83259ab48903753
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183107"
---
# <a name="servicemodel-registration-tool-servicemodelregexe"></a>Средство регистрации ServiceModel (ServiceModelReg.exe)
Этот инструмент командной строки предоставляет возможность управления регистрацией компонентов WCF и WF на одном компьютере. В обычных условиях использование данного средства не требуется, так как при установке компонентов WCF и WF производится их правильная настройка. Но если вы испытываете проблемы с активацией службы, то можно попробовать зарегистрировать компоненты с помощью этого средства.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
ServiceModelReg.exe[(-ia|-ua|-r)|((-i|-u) -c:<command>)] [-v|-q] [-nologo] [-?]  
```  
  
## <a name="remarks"></a>Remarks  
 Это средство можно найти в следующей папке:  
  
 %SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\  
  
> [!NOTE]
> Когда инструмент регистрации ServiceModel работает на Windows Vista, диалог **функций Windows** может не отражать, что опция **активации Windows Communication Foundation HTTP** под Microsoft **.NET Framework 3.0** включена. **Диалог функций Windows** можно получить, нажав **Кнопка Начало,** затем нажмите **Выполнить,** а затем набрав **OptionalFeatures**.  
  
 В следующей таблице представлены параметры, которые могут использоваться с ServiceModelReg.exe.  
  
|Параметр|Описание|  
|------------|-----------------|  
|`-ia`|Устанавливает все компоненты WCF и WF.|  
|`-ua`|Удаляет все компоненты WCF и WF.|  
|`-r`|Ремонтирует все компоненты WCF и WF.|  
|`-i`|Устанавливает компоненты WCF и WF, заданные с помощью ключа «-с».|  
|`-u`|Удаляет компоненты WCF и WF, заданные с помощью ключа «-с».|  
|`-c`|Устанавливает или удаляет компонент.<br /><br /> - httpnamespace - Резервирование пространства имен HTTP<br />- tcpportsharing - TCP портовый обмен<br />- tcpactivation - Служба активации TCP (не поддерживается на профиле клиента .NET 4)<br />- namedpipeactivation - Названная служба активации трубы (не поддерживается на профиле клиента .NET 4<br />- msmqactivation - Служба активации МСМЗ (не поддерживается на профиль клиента .NET 4<br />- etw - ETW событие отслеживания манифестов (Windows Vista или позже)|  
|`-q`|Тихий режим (только для отображения журнала ошибок)|  
|`-v`|Режим подробного вывода.|  
|`-nologo`|Подавляет вывод логотипа и сообщения об авторском праве.|  
|`-?`|Отображает текст справки|  
  
## <a name="fixing-the-fileloadexception-error"></a>Исправление ошибки FileLoadException  
 Если вы установили предыдущие версии WCF на `FileLoadFoundException` машине, вы можете получить ошибку при запуске инструмента ServiceModelReg для регистрации новой установки. Это может произойти, даже если пользователь вручную удалил файлы из каталога установки предыдущей версии, но оставил файл machine.config без изменений.  
  
 Сообщение об ошибке подобно приведенному ниже.  
  
```console  
Error: System.IO.FileLoadException: Could not load file or assembly 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies. The located assembly's manifest definition does not match the assembly reference. (Exception from HRESULT: 0x80131040)  
File name: 'System.ServiceModel, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'  
```  
  
 Из этого сообщения об ошибке можно выяснить, что сборка System.ServiceModel версии 2.0.0.0 была установлена более ранней CTP-версией. Текущая версия сборки System.ServiceModel - 3.0.0.0. Таким образом, эта проблема возникает, когда вы хотите установить официальный релиз WCF на машине, где ранний выпуск CTP WCF был установлен, но не полностью неустановлен.  
  
 ServiceModelReg.exe не может удалять записи предыдущих версий или регистрировать записи новой версии. Единственным путем обхода данной проблемы является редактирование файла machine.config вручную. Путь к этому файлу указан ниже.  
  
```console  
%windir%\Microsoft.NET\Framework\v2.0.50727\config\machine.config
```  
  
 Если вы работаете wCF на 64-разрядной машине, вы также должны отодвигать тот же файл в этом месте.  
  
```console  
%windir%\Microsoft.NET\Framework64\v2.0.50727\config\machine.config
```  
  
 Найдите в этом файле все узлы XML, которые относятся к "System.ServiceModel, Version 2.0.0.0", удалите их и любые детские узлы. Сохраните файл и повторно запустите ServiceModelReg.exe. Проблема устранена.  
  
## <a name="examples"></a>Примеры  
 В следующих примерах показано, как использовать наиболее употребимые параметры средства ServiceModelReg.exe.  
  
```console  
ServiceModelReg.exe -ia  
  Installs all components  
ServiceModelReg.exe -i -c:httpnamespace -c:etw  
  Installs HTTP namespace reservation and ETW manifests  
ServiceModelReg.exe -u -c:etw  
  Uninstalls ETW manifests  
ServiceModelReg.exe -r  
  Repairs an extended install  
```

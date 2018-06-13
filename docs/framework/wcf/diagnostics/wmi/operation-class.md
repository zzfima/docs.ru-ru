---
title: Класс Operation
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: d9256915afe9fdb8e4c91d186131fe41a7094c56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487572"
---
# <a name="operation-class"></a>Класс Operation
Операция  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс Operation не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс Operation имеет следующие свойства.  
  
### <a name="action"></a>Действие  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Действие WS-Addressing сообщения запроса.  
  
### <a name="asyncpattern"></a>AsyncPattern  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, что операция реализуется асинхронно с помощью `Begin`[открыть/закрыть угловые скобки] и `End`пары методов [открыть/закрыть угловые скобки] в контракте службы.  
  
### <a name="behaviors"></a>поведения  
 Тип данных: массив Behavior  
  
 Тип доступа: только для чтения  
  
 Поведения, связанные с этой операцией.  
  
### <a name="iscallback"></a>IsCallback  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Истинно, если операция является операцией обратного вызова.  
  
### <a name="isinitiating"></a>IsInitiating  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Показывает, реализует ли метод операцию, которая может инициировать сеанс на сервере.  
  
### <a name="isoneway"></a>IsOneWay  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Показывает, возвращает ли операция ответное сообщение.  
  
### <a name="isterminating"></a>IsTerminating  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Показывает, возвращает ли операция ответное сообщение.  
  
### <a name="methodsignature"></a>MethodSignature  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Подпись метода операции.  
  
### <a name="name"></a>name  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя операции.  
  
### <a name="parametertypes"></a>ParameterTypes  
 Тип данных: массив строк  
  
 Тип доступа: только для чтения  
  
 Типы параметров операции.  
  
### <a name="replyaction"></a>ReplyAction  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Значение действия SOAP для ответного сообщения операции.  
  
### <a name="returntype"></a>ReturnType  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Тип возвращаемого значения операции.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Description.OperationDescription>

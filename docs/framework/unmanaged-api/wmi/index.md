---
title: WMI и счетчиков производительности (Справочник по неуправляемым API)
description: .NET Framework представлены неуправляемый интерфейс API для сведений о счетчиках производительности и WMI.
author: rpetrusha
ms.author: ronpet
ms.date: 11/06/2017
ms.openlocfilehash: 2007c8aa74e1ccf3c4753343ac633b67a36daeb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462030"
---
# <a name="windows-management-instrumentation-wmi-and-performance-counters-unmanaged-api-reference"></a>Инструментарий управления Windows (WMI) и счетчиков производительности (Справочник по неуправляемым API)

Неуправляемый интерфейс API .NET Framework WMI и счетчики производительности состоит из набора функций, которые создают оболочки для вызовов [собственного API инструментария управления Windows](https://msdn.microsoft.com/library/aa389276(v=vs.85).aspx). Он позволяет разрабатывать средства и библиотеки, управление и наблюдение за удаленными компьютерами.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
API-Интерфейс включает следующие функции:

| Функция | Описание |
|---------|---------|
| [Функция BeginEnumeration](beginenumeration.md) | Устанавливает перечислитель в начало перечисления свойств объекта WMI. |
| [Функция BeginMethodEnumeration](beginmethodenumeration.md) |  Начинает перечисление методов, доступных для объекта. |
| [Функция BlessIWbemServices](blessiwbemservices.md) | Указывает, разрешить ли учетные данные пользователя доступ к указанному классу IWbemServices. |
| [Функция BlessIWbemServicesObject](blessiwbemservicesobject.md) | Указывает, является ли учетные данные пользователя предоставление доступа к объекту службы IWbem. |
| [Функция Clone](clone.md) | Возвращает новый объект, который представляет собой полный клон текущего объекта. |
| [Функция CloneEnumWbemClassObject](cloneenumwbemclassobject.md) | Создается копия логического перечислителя, сохраняя его текущую позицию в перечислении. |
| [Функция CompareTo](compareto.md) | Сравнивает объект с другим объектом управления Windows. |
| [Функция ConnectServerWmi](connectserverwmi.md) | Создает подключается через DCOM с пространством имен WMI на указанном компьютере. |
| [Функция CreateClassEnumWmi](createclassenumwmi.md) | Возвращает перечислитель для всех классов, которые удовлетворяют указанные критерии выбора. |
| [Функция CreateInstanceEnumWmi](createinstanceenumwmi.md) | Возвращает перечислитель, который возвращает принимаемые экземпляры указанного класса, который отвечает указанные критерии выбора. |
| [Функция Delete](delete.md) | Удаляет указанное свойство из определения класса и все его квалификаторов. |
| [Функция DeleteMethod](deletemethod.md) | Удаляет указанный метод из определения класса CIM. |
| [Функция EndEnumeration](endenumeration.md) | Завершает последовательность перечисления. | 
| [Функция EndMethodEnumeration](endmethodenumeration.md) | Завершает последовательность перечисления запущен с помощью вызова [BeginMethodEnumeration функция](beginmethodenumeration.md). |
| [Функция ExecNotificationQueryWmi](execnotificationquerywmi.md) | Выполняет запрос для получения событий. |
| [Функция ExecQueryWmi](execquerywmi.md) | Выполняет запрос для получения объектов. |
| [Функция FormatFromRawValue](formatfromrawvalue.md) | Преобразует одно значение данных оценки производительности в указанный формат или два значения данных для оценки производительности, если преобразование формата выполняется на основе времени. | 
| [Функция Get](get.md) | Получает значение указанного свойства, если он существует. |
| [Функция GetCurrentApartmentType](getcurrentapartmenttype.md) | Возвращает тип подразделения, в котором выполняется вызывающего объекта. |
| [Функция GetDemultiplexedStub](getdemultiplexedstub.md) | Создает приемник объект сервера пересылки для клиента при получении асинхронные вызовы от управления Windows. |
| [GetErrorInfo-функция](geterrorinfo.md) | Извлекает сведения об ошибках в предыдущем вызове функции. | 
| [Функция GetMethod](getmethod.md) | Возвращает сведения об указанном методе. | 
| [Функция GetMethodOrigin](getmethodorigin.md) | Определяет класс, в котором объявлен метод. |
| [Функция GetMethodQualifierSet](getmethodqualifierset.md) | Извлекает квалификатор для конкретного метода. |
| [Функция GetNames](getnames.md) | Возвращает подмножество или все имена свойств объекта. |
| [Функция GetObjectText](getobjecttext.md) | Возвращает текстовое отображение объекта с помощью синтаксиса MOF. | 
| [Функция GetPropertyHandle](getpropertyhandle.md) | Возвращает уникальный дескриптор, который определяет свойство. |
| [Функция GetPropertyOrigin](getpropertyorigin.md) | Определяет класс, в котором объявлено свойство. |
| [Функция GetPropertyQualifierSet](getpropertyqualifierset.md) | Извлекает квалификатор для конкретного свойства.  |
| [Функция GetQualifierSet](getqualifierset.md) | Извлекает квалификатор для экземпляра класса или определения класса. |
| [Функция раскрывшемся списке](inheritsfrom.md) | Определяет, является ли текущего класса или экземпляра является производным от класса-родителя указанного. |
| [Initialize-функция](initialize.md) | Выполняет инициализацию WMI. |
| [Функция Next](next.md) | Извлекает свойство next в перечислении. | 
| [Функция NextMethod](nextmethod.md) | Извлекает следующий метод в перечислении. |
| [PUT-функция](put.md) | Присваивает новое значение именованного свойства. |
| [Функция PutClassWmi](putclasswmi.md) | Создает новый класс, или обновляет существующую. |
| [Функция PutInstanceWmi](putinstancewmi.md) | Создает или обновляет экземпляр существующего класса. Экземпляр записывается в репозиторий WMI. |
| [Функция PutMethod](putmethod.md) | Создает метод. |
| [Функция QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) | Возвращает перечислитель квалификаторы объект в начало перечисления. |
| [Функция QualifierSet_Delete](qualifierset-delete.md) | Удаляет указанный квалификатор по имени.  |
| [Функция QualifierSet_EndEnumeration](qualifierset-endenumeration.md) | Завершается перечисление начался вызовом `QualifierSet_BeginEnumeration` функции. |
| [Функция QualifierSet_Get](qualifierset-get.md) | Возвращает указанный именованный квалификатор.  |
| [Функция QualifierSet_GetNames](qualifierset-getnames.md) | Получает имена всех квалификаторов, или указанный квалификаторов, которые доступны из текущего объекта или свойства. |
| [Функция QualifierSet_Next](qualifierset-next.md) | Извлекает следующий квалификатор в перечислении, работы с помощью вызова [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) функции. |
| [Функция QualifierSet_Put](qualifierset-put.md) | Записывает именованный квалификатор и значение. |
| [Функция ResetSecurity](resetsecurity.md) | Присваивает указанный олицетворения текущего потока. |
| [Функция SetSecurity](setsecurity.md) | Извлекает маркер олицетворения, связанный с текущим потоком. |
| [Функция SpawnDerivedClass](spawnderivedclass.md) | Создает объект вновь производного класса из указанного объекта. | 
| [Функция SpawnInstance](spawninstance.md) | Создает новый экземпляр класса. |   
| [Функция VerifyClient](verifyclientkey.md) | Гарантирует, что ключ клиента имеет неправильные параметры безопасности. |
| [Функция WritePropertyValue](writepropertyvalue.md) | Записывает указанное число байтов в свойство, идентифицируемое дескриптор свойства. |

 ## <a name="see-also"></a>См. также
[Справочник по неуправляемым API](../index.md) 

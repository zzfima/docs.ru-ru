---
title: WMI и счетчики производительности (справочник по неуправляемым API)
description: Сводные данные по неуправляемому API-интерфейсу .NET Framework для WMI и счетчиков производительности.
ms.date: 11/06/2017
ms.openlocfilehash: f28cd25ee6c3511dc5ac8a6dd4076c81f43fe74a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127419"
---
# <a name="windows-management-instrumentation-wmi-and-performance-counters-unmanaged-api-reference"></a>Инструментарий управления Windows (WMI) и счетчики производительности (справочник по неуправляемым API)

Неуправляемый API-интерфейс .NET Framework для WMI и счетчиков производительности состоит из набора функций, которые создают оболочки для вызовов [собственного API инструментария управления Windows](/windows/desktop/WmiSdk/com-api-for-wmi). Он позволяет разрабатывать средства и библиотеки для мониторинга и контроля удаленных компьютерных систем.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

API включает в себя следующие функции:

| Функция | ОПИСАНИЕ |
|---------|---------|
| [Функция BeginEnumeration](beginenumeration.md) | Сбрасывает перечислитель в начало перечисления свойств объекта WMI. |
| [Функция BeginMethodEnumeration](beginmethodenumeration.md) |  Начинает перечисление методов, доступных для объекта. |
| [Функция BlessIWbemServices](blessiwbemservices.md) | Указывает, разрешают ли учетные данные пользователя доступ к указанному классу IWbemServices. |
| [Функция BlessIWbemServicesObject](blessiwbemservicesobject.md) | Указывает, разрешают ли учетные данные пользователя доступ к указанному объекту службы IWbem. |
| [Функция Clone](clone.md) | Возвращает новый объект, который является полным клоном текущего объекта. |
| [Функция CloneEnumWbemClassObject](cloneenumwbemclassobject.md) | Создает логическую копию перечислителя, сохраняя текущую позицию в перечислении. |
| [Функция CompareTo](compareto.md) | Сравнивает объект с другим объектом управления Windows. |
| [Функция ConnectServerWmi](connectserverwmi.md) | Создает подключение через DCOM к пространству имен WMI на указанном компьютере. |
| [Функция CreateClassEnumWmi](createclassenumwmi.md) | Возвращает перечислитель для всех классов, которые удовлетворяют указанным критериям выбора. |
| [Функция CreateInstanceEnumWmi](createinstanceenumwmi.md) | Возвращает перечислитель, возвращающий экземпляры указанного класса в соответствии с заданными критериями выбора. |
| [Функция Delete](delete.md) | Удаляет из определения класса указанное свойство и все его квалификаторы. |
| [Функция DeleteMethod](deletemethod.md) | Удаляет указанный метод из определения класса CIM. |
| [Функция EndEnumeration](endenumeration.md) | Завершает последовательность перечисления. |
| [Функция EndMethodEnumeration](endmethodenumeration.md) | Завершает последовательность перечисления, начатую вызовом [функции BeginMethodEnumeration](beginmethodenumeration.md). |
| [Функция ExecNotificationQueryWmi](execnotificationquerywmi.md) | Выполняет запрос для получения событий. |
| [Функция ExecQueryWmi](execquerywmi.md) | Выполняет запрос для получения объектов. |
| [Функция FormatFromRawValue](formatfromrawvalue.md) | Преобразует одно значение необработанных данных о производительности в указанный формат или делает это для двух значений, если преобразование формата зависит от времени. |
| [Функция Get](get.md) | Получает значение указанного свойства, если оно существует. |
| [Функция GetCurrentApartmentType](getcurrentapartmenttype.md) | Получает тип подразделения, в котором выполняется вызывающий объект. |
| [Функция GetDemultiplexedStub](getdemultiplexedstub.md) | Создает приемник переадресации объекта, который помогает клиенту получать асинхронные вызовы из службы управления Windows. |
| [Функция GetErrorInfo](geterrorinfo.md) | Получает сведения об ошибках из предыдущего вызова функции. |
| [Функция GetMethod](getmethod.md) | Получает сведения об указанном методе. |
| [Функция GetMethodOrigin](getmethodorigin.md) | Определяет класс, в котором объявлен метод. |
| [Функция GetMethodQualifierSet](getmethodqualifierset.md) | Получает набор квалификаторов для определенного метода. |
| [Функция GetNames](getnames.md) | Получает подмножество имен или все имена свойств объекта. |
| [Функция GetObjectText](getobjecttext.md) | Возвращает текстовое отображение объекта в синтаксисе MOF. |
| [Функция GetPropertyHandle](getpropertyhandle.md) | Возвращает уникальный маркер, определяющий свойство. |
| [Функция GetPropertyOrigin](getpropertyorigin.md) | Определяет класс, в котором объявлено свойство. |
| [Функция GetPropertyQualifierSet](getpropertyqualifierset.md) | Получает набор квалификаторов для определенного свойства.  |
| [Функция GetQualifierSet](getqualifierset.md) | Получает набор квалификатор для экземпляра или определения класса. |
| [Функция InheritsFrom](inheritsfrom.md) | Определяет, является ли текущий класс или экземпляр производным от указанного родительского класса. |
| [Функция Initialize](initialize.md) | Инициализирует WMI. |
| [Функция Next](next.md) | Получает следующее свойство в перечислении. |
| [Функция NextMethod](nextmethod.md) | Получает следующий метод в перечислении. |
| [Функция Put](put.md) | Задает новое значение для именованного свойства. |
| [Функция PutClassWmi](putclasswmi.md) | Создает новый класс или обновляет существующий. |
| [Функция PutInstanceWmi](putinstancewmi.md) | Создает или обновляет экземпляр существующего класса. Экземпляр записывается в репозиторий WMI. |
| [Функция PutMethod](putmethod.md) | Создает метод. |
| [Функция QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) | Сбрасывает перечислитель квалификаторов объекта в начало перечисления. |
| [Функция QualifierSet_Delete](qualifierset-delete.md) | Удаляет указанный квалификатор по имени.  |
| [Функция QualifierSet_EndEnumeration](qualifierset-endenumeration.md) | Завершает перечисление, начатое вызовом функции `QualifierSet_BeginEnumeration`. |
| [Функция QualifierSet_Get](qualifierset-get.md) | Получает указанный именованный квалификатор.  |
| [Функция QualifierSet_GetNames](qualifierset-getnames.md) | Получает имена всех или указанных квалификаторов, доступных из текущего объекта или свойства. |
| [Функция QualifierSet_Next](qualifierset-next.md) | Получает следующий квалификатор в перечислении, начатом вызовом функции [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
| [Функция QualifierSet_Put](qualifierset-put.md) | Записывает именованный квалификатор и значение. |
| [Функция ResetSecurity](resetsecurity.md) | Назначает предоставленный маркер олицетворения текущему потоку. |
| [Функция SetSecurity](setsecurity.md) | Получает маркер олицетворения, связанный с текущим потоком. |
| [Функция SpawnDerivedClass](spawnderivedclass.md) | Создает объект производного класса из указанного объекта. |
| [Функция SpawnInstance](spawninstance.md) | Создает экземпляр класса. |
| [Функция VerifyClient](verifyclientkey.md) | Проверяет, что ключ клиента имеет верные параметры безопасности. |
| [Функция WritePropertyValue](writepropertyvalue.md) | Записывает указанное число байт в свойство, заданное маркером свойства. |

## <a name="see-also"></a>См. также

- [Справочник по неуправляемым API](../index.md)

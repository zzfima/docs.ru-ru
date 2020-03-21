---
title: Получите образцы баз данных S'L Server для ADO.NET образцов кода
description: Загрузите образцы баз данных S'L Server, используемые в образцах кода в документации ADO.NET, а также инструменты s'L Server и управления
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 19d659cbe8f39d27b71dc59c738355f12fce92a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148391"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Получить образцы баз данных для образцов кода ADO.NET

В ряде примеров и пошагов в документации [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] используются образцы баз данных сервера S'L ИС ИСИ И. Вы можете скачать эти продукты бесплатно от Microsoft.

## <a name="get-the-northwind-sample-database-for-sql-server"></a>Получение выборочной базы данных Northwind для сервера S'L

Загрузите `instnwnd.sql` скрипт из следующего репозитория GitHub для создания и загрузки выборочной базы данных Northwind для сервера S'L:

[Нортвинд и пабы образцы баз данных для Microsoft S'L Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

Прежде чем использовать базу данных Northwind, необходимо `instnwnd.sql` запустить загруженный файл скрипта, чтобы воссоздать базу данных на экземпляре сервера S'L, используя [студию управления серверами S'L](#get_ssms) или аналогичный инструмент. Следуйте инструкциям в файле Readme в репозитории.

> [!TIP]
> Если вы ищете базу данных Northwind для Microsoft Access, [см.](#northwind_access)

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a>Получить образец базы данных Northwind для Microsoft Access

Образная база данных Northwind для Microsoft Access недоступна в Центре загрузки Майкрософт. Чтобы установить Northwind непосредственно из Access, сделайте следующие вещи:

1. Открытый доступ.

1. Введите **Northwind** в поле **поиска онлайн шаблонов,** а затем выберите **Enter.**

1. На экране результатов выберите **Northwind**. Новое окно открывается с описанием базы данных Northwind.

1. В новом окне, в текстовом окне **имя файла,** укажите имя файла для вашей копии базы данных Northwind.

1. Выберите **Создать**. Access загружает базу данных Northwind и готовит файл.

1. Когда этот процесс завершен, база данных открывается с экрана Welcome.

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>Получить образец базы данных AdventureWorks для сервера S'L

Загрузите образец базы данных AdventureWorks для сервера S'L из следующего репозитория GitHub:

[Образцы баз данных AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

После загрузки одного из файлов\*резервного копирования базы данных (.bak) восстановите резервную часть в экземпляре сервера S'L, используя s'L Server Management Studio (SSMS). Подробнее о [том, как получить студию управления серверами S'L](#get_ssms).

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a>Получите студию управления серверами S'L
Если вы хотите просмотреть или изменить загруженную базу данных, вы можете использовать студию управления серверами S'L (SSMS). Скачать SSMS со следующей страницы:

[Скачивание SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms)

Вы также можете просматривать и управлять базами данных в интегрированной среде разработки Visual Studio (IDE). В [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)подключитесь к базе данных из **S'L Server Object Explorer**или создайте подключение к базе данных в Server **Explorer.** Откройте эти панели исследователей из меню **View.**

## <a name="get-sql-server-express"></a><a name="get_sql"></a>Получить сервер экспресс S'L

S'L Server Express — это бесплатное издание сервера начального уровня, которое можно перераспределить с помощью приложений. Скачать серверный экспресс s'L со следующей страницы:
  
[SQL Server Express Edition](https://www.microsoft.com/sql-server/sql-server-editions-express)

Если вы используете [Visual Studio,](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)S'L Server Express LocalDB включен в бесплатное издание Сообщества Visual Studio, а также профессиональные и более высокие издания.  

## <a name="see-also"></a>См. также раздел

- [Начало работы](getting-started.md)

---
title: Получение образца SQL Server баз данных для примеров кода ADO.NET
description: Скачайте пример SQL Server баз данных, используемых в примерах кода в документации по ADO.NET, а также SQL Server и средств управления.
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 60566041ff4f99e96c9aee052dbcc17b5e5da9e5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794028"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Получение образцов баз данных для примеров кода ADO.NET

Некоторые примеры и пошаговые руководства в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] документации используют пример SQL Server баз данных и SQL Server Express. Эти продукты можно бесплатно загрузить с веб – Майкрософт.

## <a name="get-the-northwind-sample-database-for-sql-server"></a>Получение образца базы данных Northwind для SQL Server

Скачайте скрипт `instnwnd.sql` из следующего репозитория GitHub, чтобы создать и загрузить образец базы данных Northwind для SQL Server:

[Учебные базы данных Northwind и Pubs для Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

Прежде чем можно будет использовать базу данных Northwind, необходимо запустить скачанный `instnwnd.sql` файл скрипта, чтобы повторно создать базу данных на экземпляре SQL Server с помощью [SQL Server Management Studio](#get_ssms) или аналогичного средства. Следуйте инструкциям в файле сведений в репозитории.

> [!TIP]
> Если вы ищете базу данных Northwind для Microsoft Access, см. статью [Установка образца базы данных Northwind для Microsoft Access](#northwind_access).

## <a name="northwind_access"></a>Получение образца базы данных Northwind для Microsoft Access

Образец базы данных Northwind для Microsoft Access недоступен в центре загрузки Майкрософт. Чтобы установить Northwind непосредственно из Access, выполните следующие действия.

1. Откройте Access.

1. В поле **Поиск шаблонов в Интернете** введите **Northwind** , а затем нажмите клавишу **Ввод**.

1. На экране результатов выберите **Northwind**. Откроется новое окно с описанием базы данных Northwind.

1. В новом окне в текстовом поле **имя файла** укажите имя файла для копии базы данных Northwind.

1. Нажмите кнопку **Создать**. Access загружает базу данных Northwind и готовит файл.

1. После завершения этого процесса база данных откроется с экраном приветствия.

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>Получение образца базы данных AdventureWorks для SQL Server

Скачайте образец базы данных AdventureWorks для SQL Server из следующего репозитория GitHub:

[Образцы баз данных AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

После загрузки одного из файлов резервной копии базы\*данных (BAK) восстановите резервную копию на экземпляре SQL Server с помощью SQL Server Management Studio (SSMS). См. раздел [Get SQL Server Management Studio](#get_ssms).

## <a name="get_ssms"></a>Получить SQL Server Management Studio
Если вы хотите просмотреть или изменить загруженную базу данных, можно использовать SQL Server Management Studio (SSMS). Скачайте среду SSMS со следующей страницы:

[Загрузка SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms) 

Вы также можете просматривать базы данных и управлять ими в интегрированной среде разработки Visual Studio (IDE). В [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)подключитесь к базе данных из **Обозреватель объектов SQL Server**или создайте подключение к базе данных в **Обозреватель сервера**. Откройте эти панели обозревателя в меню **вид** .

## <a name="get_sql"></a>Получить SQL Server Express

SQL Server Express — это бесплатный выпуск SQL Server, который можно распространять вместе с приложениями. Скачайте SQL Server Express со следующей страницы:
  
[Выпуск SQL Server Express](https://www.microsoft.com/sql-server/sql-server-editions-express)

Если вы используете [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB входит в бесплатный выпуск сообщества Visual Studio, а также в профессиональный и более поздние версии.  

## <a name="see-also"></a>См. также

- [Начало работы](getting-started.md)

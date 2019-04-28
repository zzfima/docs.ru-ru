---
title: Практическое руководство. Добавление ссылки на службу данных (службы данных WCF)
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: fc1786e1c6102c702374989253cd3ce23e3f7b54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765535"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>Практическое руководство. Добавление ссылки на службу данных (службы данных WCF)

Можно использовать **Add Service Reference** диалоговое окно в Visual Studio для добавления ссылки на службы WCF Data Services. Это позволяет упростить доступ к службе данных в клиентском приложении, разрабатываемом в среде Visual Studio. По завершении этой процедуры формируются классы данных на основе метаданных, полученных от службы данных. Дополнительные сведения см. в разделе [Создание клиентской библиотеки службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).

## <a name="add-a-data-service-reference"></a>Добавьте ссылку на службу данных

1. Если служба данных не является частью решения и пока не запущена, запустите ее и отметьте ее URI. (Необязательно.)

2. В Visual Studio в **обозревателе решений**, щелкните правой кнопкой мыши клиентский проект и выберите **добавить** > **ссылки на службу**.

3. Если служба данных является частью текущего решения, нажмите кнопку **Discover**.

     -или-

     В **адрес** текстовом поле Введите базовый URL-адрес службы данных, такие как `http://localhost:1234/Northwind.svc`, а затем нажмите кнопку **Go**.

4. Нажмите кнопку **ОК**.

     В проект добавляется новый файл кода, содержащий классы данных, доступа и работе с ресурсами службы данных.

## <a name="see-also"></a>См. также

- [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
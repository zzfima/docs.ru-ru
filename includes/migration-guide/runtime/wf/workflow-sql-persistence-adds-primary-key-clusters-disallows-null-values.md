---
ms.openlocfilehash: 9e98d3bca645cf82bf4fe99160dd096b0e274ef7
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760443"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="5eb01-101">Функция сохраняемости SQL для рабочего процесса добавляет кластеры первичных ключей и не допускает значения NULL в некоторых столбцах</span><span class="sxs-lookup"><span data-stu-id="5eb01-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

|   |   |
|---|---|
|<span data-ttu-id="5eb01-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="5eb01-102">Details</span></span>|<span data-ttu-id="5eb01-103">Начиная с версии .NET Framework 4.7, таблицы, созданные для хранилища экземпляров рабочего процесса SQL (SWIS) с помощью скрипта SqlWorkflowInstanceStoreSchema.sql, используют кластеризованные первичные ключи.</span><span class="sxs-lookup"><span data-stu-id="5eb01-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="5eb01-104">Из-за этого удостоверения не поддерживают значения <code>null</code>.</span><span class="sxs-lookup"><span data-stu-id="5eb01-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="5eb01-105">Это изменение не влияет на работу SWIS.</span><span class="sxs-lookup"><span data-stu-id="5eb01-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="5eb01-106">Были внесены обновления в поддержку механизма репликации транзакций SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5eb01-106">The updates were made to support SQL Server Transactional Replication.</span></span>|
|<span data-ttu-id="5eb01-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="5eb01-107">Suggestion</span></span>|<span data-ttu-id="5eb01-108">Чтобы реализовать это изменение, в существующую установку необходимо добавить SQL-файл SqlWorkflowInstanceStoreSchemaUpgrade.sql.</span><span class="sxs-lookup"><span data-stu-id="5eb01-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="5eb01-109">В новых установках баз данных это изменение реализуется автоматически.</span><span class="sxs-lookup"><span data-stu-id="5eb01-109">New database installations will automatically have the change.</span></span>|
|<span data-ttu-id="5eb01-110">Область</span><span class="sxs-lookup"><span data-stu-id="5eb01-110">Scope</span></span>|<span data-ttu-id="5eb01-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="5eb01-111">Edge</span></span>|
|<span data-ttu-id="5eb01-112">Версия</span><span class="sxs-lookup"><span data-stu-id="5eb01-112">Version</span></span>|<span data-ttu-id="5eb01-113">4.7</span><span class="sxs-lookup"><span data-stu-id="5eb01-113">4.7</span></span>|
|<span data-ttu-id="5eb01-114">Тип</span><span class="sxs-lookup"><span data-stu-id="5eb01-114">Type</span></span>|<span data-ttu-id="5eb01-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="5eb01-115">Runtime</span></span>|


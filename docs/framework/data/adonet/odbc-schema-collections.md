---
title: Коллекции схемы ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772051"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="80ab8-102">Коллекции схемы ODBC</span><span class="sxs-lookup"><span data-stu-id="80ab8-102">ODBC Schema Collections</span></span>

<span data-ttu-id="80ab8-103">В данном разделе рассматривается поддержка коллекций схем для драйверов ODBC для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="80ab8-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="80ab8-104">Драйвер ODBC для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="80ab8-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="80ab8-105">Драйвер ODBC для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="80ab8-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="80ab8-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="80ab8-106">Tables</span></span>

- <span data-ttu-id="80ab8-107">Индексы</span><span class="sxs-lookup"><span data-stu-id="80ab8-107">Indexes</span></span>

- <span data-ttu-id="80ab8-108">Столбцы</span><span class="sxs-lookup"><span data-stu-id="80ab8-108">Columns</span></span>

- <span data-ttu-id="80ab8-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="80ab8-109">Procedures</span></span>

- <span data-ttu-id="80ab8-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="80ab8-110">ProcedureColumns</span></span>

- <span data-ttu-id="80ab8-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="80ab8-111">ProcedureParameters</span></span>

- <span data-ttu-id="80ab8-112">Представления</span><span class="sxs-lookup"><span data-stu-id="80ab8-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="80ab8-113">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="80ab8-113">Tables and Views</span></span>

|<span data-ttu-id="80ab8-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-114">ColumnName</span></span>|<span data-ttu-id="80ab8-115">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="80ab8-116">TABLE_CAT</span></span>|<span data-ttu-id="80ab8-117">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-117">String</span></span>|
|<span data-ttu-id="80ab8-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="80ab8-118">TABLE_SCHEM</span></span>|<span data-ttu-id="80ab8-119">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-119">String</span></span>|
|<span data-ttu-id="80ab8-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-120">TABLE_NAME</span></span>|<span data-ttu-id="80ab8-121">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-121">String</span></span>|
|<span data-ttu-id="80ab8-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-122">TABLE_TYPE</span></span>|<span data-ttu-id="80ab8-123">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-123">String</span></span>|
|<span data-ttu-id="80ab8-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-124">REMARKS</span></span>|<span data-ttu-id="80ab8-125">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="80ab8-126">Индексы</span><span class="sxs-lookup"><span data-stu-id="80ab8-126">Indexes</span></span>

|<span data-ttu-id="80ab8-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-127">ColumnName</span></span>|<span data-ttu-id="80ab8-128">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="80ab8-129">TABLE_CAT</span></span>|<span data-ttu-id="80ab8-130">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-130">String</span></span>|
|<span data-ttu-id="80ab8-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="80ab8-131">TABLE_SCHEM</span></span>|<span data-ttu-id="80ab8-132">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-132">String</span></span>|
|<span data-ttu-id="80ab8-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-133">TABLE_NAME</span></span>|<span data-ttu-id="80ab8-134">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-134">String</span></span>|
|<span data-ttu-id="80ab8-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="80ab8-135">NON_UNIQUE</span></span>|<span data-ttu-id="80ab8-136">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-136">Int16</span></span>|
|<span data-ttu-id="80ab8-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="80ab8-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="80ab8-138">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-138">String</span></span>|
|<span data-ttu-id="80ab8-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-139">INDEX_NAME</span></span>|<span data-ttu-id="80ab8-140">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-140">String</span></span>|
|<span data-ttu-id="80ab8-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-141">TYPE</span></span>|<span data-ttu-id="80ab8-142">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-142">Int16</span></span>|
|<span data-ttu-id="80ab8-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="80ab8-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="80ab8-144">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-144">Int16</span></span>|
|<span data-ttu-id="80ab8-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-145">COLUMN_NAME</span></span>|<span data-ttu-id="80ab8-146">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-146">String</span></span>|
|<span data-ttu-id="80ab8-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="80ab8-147">ASC_OR_DESC</span></span>|<span data-ttu-id="80ab8-148">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-148">String</span></span>|
|<span data-ttu-id="80ab8-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="80ab8-149">CARDINALITY</span></span>|<span data-ttu-id="80ab8-150">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-150">Int32</span></span>|
|<span data-ttu-id="80ab8-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="80ab8-151">PAGES</span></span>|<span data-ttu-id="80ab8-152">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-152">Int32</span></span>|
|<span data-ttu-id="80ab8-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="80ab8-153">FILTER_CONDITION</span></span>|<span data-ttu-id="80ab8-154">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-154">String</span></span>|
|<span data-ttu-id="80ab8-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="80ab8-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="80ab8-156">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-156">String</span></span>|
|<span data-ttu-id="80ab8-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="80ab8-158">Byte</span><span class="sxs-lookup"><span data-stu-id="80ab8-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="80ab8-159">Столбцы</span><span class="sxs-lookup"><span data-stu-id="80ab8-159">Columns</span></span>

|<span data-ttu-id="80ab8-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-160">ColumnName</span></span>|<span data-ttu-id="80ab8-161">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="80ab8-162">TABLE_CAT</span></span>|<span data-ttu-id="80ab8-163">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-163">String</span></span>|
|<span data-ttu-id="80ab8-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="80ab8-164">TABLE_SCHEM</span></span>|<span data-ttu-id="80ab8-165">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-165">String</span></span>|
|<span data-ttu-id="80ab8-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-166">TABLE_NAME</span></span>|<span data-ttu-id="80ab8-167">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-167">String</span></span>|
|<span data-ttu-id="80ab8-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-168">COLUMN_NAME</span></span>|<span data-ttu-id="80ab8-169">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-169">String</span></span>|
|<span data-ttu-id="80ab8-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-170">DATA_TYPE</span></span>|<span data-ttu-id="80ab8-171">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-171">Int16</span></span>|
|<span data-ttu-id="80ab8-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-172">TYPE_NAME</span></span>|<span data-ttu-id="80ab8-173">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-173">String</span></span>|
|<span data-ttu-id="80ab8-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="80ab8-174">COLUMN_SIZE</span></span>|<span data-ttu-id="80ab8-175">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-175">Int32</span></span>|
|<span data-ttu-id="80ab8-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="80ab8-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="80ab8-177">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-177">Int32</span></span>|
|<span data-ttu-id="80ab8-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="80ab8-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="80ab8-179">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-179">Int16</span></span>|
|<span data-ttu-id="80ab8-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="80ab8-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="80ab8-181">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-181">Int16</span></span>|
|<span data-ttu-id="80ab8-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="80ab8-182">NULLABLE</span></span>|<span data-ttu-id="80ab8-183">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-183">Int16</span></span>|
|<span data-ttu-id="80ab8-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-184">REMARKS</span></span>|<span data-ttu-id="80ab8-185">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-185">String</span></span>|
|<span data-ttu-id="80ab8-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="80ab8-186">COLUMN_DEF</span></span>|<span data-ttu-id="80ab8-187">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-187">String</span></span>|
|<span data-ttu-id="80ab8-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="80ab8-189">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-189">Int16</span></span>|
|<span data-ttu-id="80ab8-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="80ab8-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="80ab8-191">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-191">Int16</span></span>|
|<span data-ttu-id="80ab8-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="80ab8-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="80ab8-193">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-193">Int32</span></span>|
|<span data-ttu-id="80ab8-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="80ab8-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="80ab8-195">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-195">Int32</span></span>|
|<span data-ttu-id="80ab8-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="80ab8-196">IS_NULLABLE</span></span>|<span data-ttu-id="80ab8-197">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-197">String</span></span>|
|<span data-ttu-id="80ab8-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="80ab8-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="80ab8-199">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-199">String</span></span>|
|<span data-ttu-id="80ab8-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="80ab8-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="80ab8-201">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-201">String</span></span>|
|<span data-ttu-id="80ab8-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="80ab8-203">Byte</span><span class="sxs-lookup"><span data-stu-id="80ab8-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="80ab8-204">Процедуры</span><span class="sxs-lookup"><span data-stu-id="80ab8-204">Procedures</span></span>

|<span data-ttu-id="80ab8-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-205">ColumnName</span></span>|<span data-ttu-id="80ab8-206">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="80ab8-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="80ab8-208">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-208">String</span></span>|
|<span data-ttu-id="80ab8-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="80ab8-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="80ab8-210">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-210">String</span></span>|
|<span data-ttu-id="80ab8-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="80ab8-212">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-212">String</span></span>|
|<span data-ttu-id="80ab8-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="80ab8-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="80ab8-214">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-214">Int32</span></span>|
|<span data-ttu-id="80ab8-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="80ab8-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="80ab8-216">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-216">Int32</span></span>|
|<span data-ttu-id="80ab8-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="80ab8-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="80ab8-218">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-218">Int32</span></span>|
|<span data-ttu-id="80ab8-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-219">REMARKS</span></span>|<span data-ttu-id="80ab8-220">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-220">String</span></span>|
|<span data-ttu-id="80ab8-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="80ab8-222">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="80ab8-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="80ab8-223">ProcedureColumns</span></span>

|<span data-ttu-id="80ab8-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-224">ColumnName</span></span>|<span data-ttu-id="80ab8-225">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="80ab8-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="80ab8-227">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-227">String</span></span>|
|<span data-ttu-id="80ab8-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="80ab8-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="80ab8-229">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-229">String</span></span>|
|<span data-ttu-id="80ab8-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="80ab8-231">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-231">String</span></span>|
|<span data-ttu-id="80ab8-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-232">COLUMN_NAME</span></span>|<span data-ttu-id="80ab8-233">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-233">String</span></span>|
|<span data-ttu-id="80ab8-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-234">COLUMN_TYPE</span></span>|<span data-ttu-id="80ab8-235">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-235">Int16</span></span>|
|<span data-ttu-id="80ab8-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-236">DATA_TYPE</span></span>|<span data-ttu-id="80ab8-237">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-237">Int16</span></span>|
|<span data-ttu-id="80ab8-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-238">TYPE_NAME</span></span>|<span data-ttu-id="80ab8-239">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-239">String</span></span>|
|<span data-ttu-id="80ab8-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="80ab8-240">COLUMN_SIZE</span></span>|<span data-ttu-id="80ab8-241">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-241">Int32</span></span>|
|<span data-ttu-id="80ab8-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="80ab8-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="80ab8-243">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-243">Int32</span></span>|
|<span data-ttu-id="80ab8-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="80ab8-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="80ab8-245">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-245">Int16</span></span>|
|<span data-ttu-id="80ab8-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="80ab8-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="80ab8-247">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-247">Int16</span></span>|
|<span data-ttu-id="80ab8-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="80ab8-248">NULLABLE</span></span>|<span data-ttu-id="80ab8-249">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-249">Int16</span></span>|
|<span data-ttu-id="80ab8-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-250">REMARKS</span></span>|<span data-ttu-id="80ab8-251">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-251">String</span></span>|
|<span data-ttu-id="80ab8-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="80ab8-252">COLUMN_DEF</span></span>|<span data-ttu-id="80ab8-253">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-253">String</span></span>|
|<span data-ttu-id="80ab8-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="80ab8-255">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-255">Int16</span></span>|
|<span data-ttu-id="80ab8-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="80ab8-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="80ab8-257">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-257">Int16</span></span>|
|<span data-ttu-id="80ab8-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="80ab8-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="80ab8-259">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-259">Int32</span></span>|
|<span data-ttu-id="80ab8-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="80ab8-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="80ab8-261">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-261">Int32</span></span>|
|<span data-ttu-id="80ab8-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="80ab8-262">IS_NULLABLE</span></span>|<span data-ttu-id="80ab8-263">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-263">String</span></span>|
|<span data-ttu-id="80ab8-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="80ab8-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="80ab8-265">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-265">String</span></span>|
|<span data-ttu-id="80ab8-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="80ab8-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="80ab8-267">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-267">String</span></span>|
|<span data-ttu-id="80ab8-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="80ab8-269">Byte</span><span class="sxs-lookup"><span data-stu-id="80ab8-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="80ab8-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="80ab8-270">ProcedureParameters</span></span>

|<span data-ttu-id="80ab8-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-271">ColumnName</span></span>|<span data-ttu-id="80ab8-272">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="80ab8-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="80ab8-274">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-274">String</span></span>|
|<span data-ttu-id="80ab8-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="80ab8-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="80ab8-276">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-276">String</span></span>|
|<span data-ttu-id="80ab8-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="80ab8-278">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-278">String</span></span>|
|<span data-ttu-id="80ab8-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-279">COLUMN_NAME</span></span>|<span data-ttu-id="80ab8-280">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-280">String</span></span>|
|<span data-ttu-id="80ab8-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-281">COLUMN_TYPE</span></span>|<span data-ttu-id="80ab8-282">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-282">Int16</span></span>|
|<span data-ttu-id="80ab8-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-283">DATA_TYPE</span></span>|<span data-ttu-id="80ab8-284">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-284">Int16</span></span>|
|<span data-ttu-id="80ab8-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-285">TYPE_NAME</span></span>|<span data-ttu-id="80ab8-286">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-286">String</span></span>|
|<span data-ttu-id="80ab8-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="80ab8-287">COLUMN_SIZE</span></span>|<span data-ttu-id="80ab8-288">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-288">Int32</span></span>|
|<span data-ttu-id="80ab8-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="80ab8-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="80ab8-290">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-290">Int32</span></span>|
|<span data-ttu-id="80ab8-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="80ab8-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="80ab8-292">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-292">Int16</span></span>|
|<span data-ttu-id="80ab8-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="80ab8-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="80ab8-294">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-294">Int16</span></span>|
|<span data-ttu-id="80ab8-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="80ab8-295">NULLABLE</span></span>|<span data-ttu-id="80ab8-296">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-296">Int16</span></span>|
|<span data-ttu-id="80ab8-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-297">REMARKS</span></span>|<span data-ttu-id="80ab8-298">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-298">String</span></span>|
|<span data-ttu-id="80ab8-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="80ab8-299">COLUMN_DEF</span></span>|<span data-ttu-id="80ab8-300">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-300">String</span></span>|
|<span data-ttu-id="80ab8-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="80ab8-302">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-302">Int16</span></span>|
|<span data-ttu-id="80ab8-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="80ab8-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="80ab8-304">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-304">Int16</span></span>|
|<span data-ttu-id="80ab8-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="80ab8-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="80ab8-306">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-306">Int32</span></span>|
|<span data-ttu-id="80ab8-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="80ab8-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="80ab8-308">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-308">Int32</span></span>|
|<span data-ttu-id="80ab8-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="80ab8-309">IS_NULLABLE</span></span>|<span data-ttu-id="80ab8-310">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-310">String</span></span>|
|<span data-ttu-id="80ab8-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="80ab8-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="80ab8-312">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-312">String</span></span>|
|<span data-ttu-id="80ab8-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="80ab8-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="80ab8-314">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-314">String</span></span>|
|<span data-ttu-id="80ab8-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="80ab8-316">Byte</span><span class="sxs-lookup"><span data-stu-id="80ab8-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="80ab8-317">Драйвер ODBC для Oracle (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="80ab8-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="80ab8-318">Microsoft SQL Server драйвер ODBC для Oracle поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="80ab8-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="80ab8-319">Таблицы</span><span class="sxs-lookup"><span data-stu-id="80ab8-319">Tables</span></span>

- <span data-ttu-id="80ab8-320">Столбцы</span><span class="sxs-lookup"><span data-stu-id="80ab8-320">Columns</span></span>

- <span data-ttu-id="80ab8-321">Процедуры</span><span class="sxs-lookup"><span data-stu-id="80ab8-321">Procedures</span></span>

- <span data-ttu-id="80ab8-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="80ab8-322">ProcedureColumns</span></span>

- <span data-ttu-id="80ab8-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="80ab8-323">ProcedureParameters</span></span>

- <span data-ttu-id="80ab8-324">Представления</span><span class="sxs-lookup"><span data-stu-id="80ab8-324">Views</span></span>

- <span data-ttu-id="80ab8-325">Индексы</span><span class="sxs-lookup"><span data-stu-id="80ab8-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="80ab8-326">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="80ab8-326">Tables and Views</span></span>

|<span data-ttu-id="80ab8-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-327">ColumnName</span></span>|<span data-ttu-id="80ab8-328">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="80ab8-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="80ab8-330">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-330">String</span></span>|
|<span data-ttu-id="80ab8-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="80ab8-331">TABLE_OWNER</span></span>|<span data-ttu-id="80ab8-332">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-332">String</span></span>|
|<span data-ttu-id="80ab8-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-333">TABLE_NAME</span></span>|<span data-ttu-id="80ab8-334">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-334">String</span></span>|
|<span data-ttu-id="80ab8-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-335">TABLE_TYPE</span></span>|<span data-ttu-id="80ab8-336">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-336">String</span></span>|
|<span data-ttu-id="80ab8-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-337">REMARKS</span></span>|<span data-ttu-id="80ab8-338">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="80ab8-339">Столбцы</span><span class="sxs-lookup"><span data-stu-id="80ab8-339">Columns</span></span>

|<span data-ttu-id="80ab8-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-340">ColumnName</span></span>|<span data-ttu-id="80ab8-341">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="80ab8-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="80ab8-343">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-343">String</span></span>|
|<span data-ttu-id="80ab8-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="80ab8-344">TABLE_OWNER</span></span>|<span data-ttu-id="80ab8-345">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-345">String</span></span>|
|<span data-ttu-id="80ab8-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-346">TABLE_NAME</span></span>|<span data-ttu-id="80ab8-347">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-347">String</span></span>|
|<span data-ttu-id="80ab8-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-348">COLUMN_NAME</span></span>|<span data-ttu-id="80ab8-349">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-349">String</span></span>|
|<span data-ttu-id="80ab8-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-350">DATA_TYPE</span></span>|<span data-ttu-id="80ab8-351">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-351">Int16</span></span>|
|<span data-ttu-id="80ab8-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-352">TYPE_NAME</span></span>|<span data-ttu-id="80ab8-353">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-353">String</span></span>|
|<span data-ttu-id="80ab8-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="80ab8-354">PRECISION</span></span>|<span data-ttu-id="80ab8-355">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-355">Int32</span></span>|
|<span data-ttu-id="80ab8-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="80ab8-356">LENGTH</span></span>|<span data-ttu-id="80ab8-357">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-357">Int32</span></span>|
|<span data-ttu-id="80ab8-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="80ab8-358">SCALE</span></span>|<span data-ttu-id="80ab8-359">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-359">Int16</span></span>|
|<span data-ttu-id="80ab8-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="80ab8-360">RADIX</span></span>|<span data-ttu-id="80ab8-361">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-361">Int16</span></span>|
|<span data-ttu-id="80ab8-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="80ab8-362">NULLABLE</span></span>|<span data-ttu-id="80ab8-363">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-363">Int16</span></span>|
|<span data-ttu-id="80ab8-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-364">REMARKS</span></span>|<span data-ttu-id="80ab8-365">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-365">String</span></span>|
|<span data-ttu-id="80ab8-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="80ab8-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="80ab8-367">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="80ab8-368">Процедуры</span><span class="sxs-lookup"><span data-stu-id="80ab8-368">Procedures</span></span>

|<span data-ttu-id="80ab8-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-369">ColumnName</span></span>|<span data-ttu-id="80ab8-370">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="80ab8-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="80ab8-372">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-372">String</span></span>|
|<span data-ttu-id="80ab8-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="80ab8-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="80ab8-374">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-374">String</span></span>|
|<span data-ttu-id="80ab8-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="80ab8-376">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-376">String</span></span>|
|<span data-ttu-id="80ab8-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="80ab8-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="80ab8-378">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-378">Int16</span></span>|
|<span data-ttu-id="80ab8-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="80ab8-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="80ab8-380">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-380">Int16</span></span>|
|<span data-ttu-id="80ab8-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="80ab8-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="80ab8-382">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-382">Int16</span></span>|
|<span data-ttu-id="80ab8-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-383">REMARKS</span></span>|<span data-ttu-id="80ab8-384">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-384">String</span></span>|
|<span data-ttu-id="80ab8-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="80ab8-386">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="80ab8-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="80ab8-387">ProcedureColumns</span></span>

|<span data-ttu-id="80ab8-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-388">ColumnName</span></span>|<span data-ttu-id="80ab8-389">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="80ab8-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="80ab8-391">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-391">String</span></span>|
|<span data-ttu-id="80ab8-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="80ab8-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="80ab8-393">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-393">String</span></span>|
|<span data-ttu-id="80ab8-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="80ab8-395">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-395">String</span></span>|
|<span data-ttu-id="80ab8-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-396">COLUMN_NAME</span></span>|<span data-ttu-id="80ab8-397">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-397">String</span></span>|
|<span data-ttu-id="80ab8-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-398">COLUMN_TYPE</span></span>|<span data-ttu-id="80ab8-399">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-399">Int16</span></span>|
|<span data-ttu-id="80ab8-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-400">DATA_TYPE</span></span>|<span data-ttu-id="80ab8-401">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-401">Int16</span></span>|
|<span data-ttu-id="80ab8-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-402">TYPE_NAME</span></span>|<span data-ttu-id="80ab8-403">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-403">String</span></span>|
|<span data-ttu-id="80ab8-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="80ab8-404">PRECISION</span></span>|<span data-ttu-id="80ab8-405">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-405">Int32</span></span>|
|<span data-ttu-id="80ab8-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="80ab8-406">LENGTH</span></span>|<span data-ttu-id="80ab8-407">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-407">Int32</span></span>|
|<span data-ttu-id="80ab8-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="80ab8-408">SCALE</span></span>|<span data-ttu-id="80ab8-409">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-409">Int16</span></span>|
|<span data-ttu-id="80ab8-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="80ab8-410">RADIX</span></span>|<span data-ttu-id="80ab8-411">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-411">Int16</span></span>|
|<span data-ttu-id="80ab8-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="80ab8-412">NULLABLE</span></span>|<span data-ttu-id="80ab8-413">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-413">Int16</span></span>|
|<span data-ttu-id="80ab8-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-414">REMARKS</span></span>|<span data-ttu-id="80ab8-415">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-415">String</span></span>|
|<span data-ttu-id="80ab8-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="80ab8-416">OVERLOAD</span></span>|<span data-ttu-id="80ab8-417">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-417">Int32</span></span>|
|<span data-ttu-id="80ab8-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="80ab8-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="80ab8-419">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="80ab8-420">Драйвер ODBC для Jet (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="80ab8-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="80ab8-421">Драйвер ODBC для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="80ab8-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="80ab8-422">Таблицы</span><span class="sxs-lookup"><span data-stu-id="80ab8-422">Tables</span></span>

- <span data-ttu-id="80ab8-423">Индексы</span><span class="sxs-lookup"><span data-stu-id="80ab8-423">Indexes</span></span>

- <span data-ttu-id="80ab8-424">Столбцы</span><span class="sxs-lookup"><span data-stu-id="80ab8-424">Columns</span></span>

- <span data-ttu-id="80ab8-425">Процедуры</span><span class="sxs-lookup"><span data-stu-id="80ab8-425">Procedures</span></span>

- <span data-ttu-id="80ab8-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="80ab8-426">ProcedureColumns</span></span>

- <span data-ttu-id="80ab8-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="80ab8-427">ProcedureParameters</span></span>

- <span data-ttu-id="80ab8-428">Представления</span><span class="sxs-lookup"><span data-stu-id="80ab8-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="80ab8-429">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="80ab8-429">Tables and Views</span></span>

|<span data-ttu-id="80ab8-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-430">ColumnName</span></span>|<span data-ttu-id="80ab8-431">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="80ab8-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="80ab8-433">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-433">String</span></span>|
|<span data-ttu-id="80ab8-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="80ab8-434">TABLE_OWNER</span></span>|<span data-ttu-id="80ab8-435">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-435">String</span></span>|
|<span data-ttu-id="80ab8-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-436">TABLE_NAME</span></span>|<span data-ttu-id="80ab8-437">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-437">String</span></span>|
|<span data-ttu-id="80ab8-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-438">TABLE_TYPE</span></span>|<span data-ttu-id="80ab8-439">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-439">String</span></span>|
|<span data-ttu-id="80ab8-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-440">REMARKS</span></span>|<span data-ttu-id="80ab8-441">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="80ab8-442">Столбцы</span><span class="sxs-lookup"><span data-stu-id="80ab8-442">Columns</span></span>

|<span data-ttu-id="80ab8-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-443">ColumnName</span></span>|<span data-ttu-id="80ab8-444">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="80ab8-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="80ab8-446">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-446">String</span></span>|
|<span data-ttu-id="80ab8-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="80ab8-447">TABLE_OWNER</span></span>|<span data-ttu-id="80ab8-448">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-448">String</span></span>|
|<span data-ttu-id="80ab8-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-449">TABLE_NAME</span></span>|<span data-ttu-id="80ab8-450">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-450">String</span></span>|
|<span data-ttu-id="80ab8-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-451">COLUMN_NAME</span></span>|<span data-ttu-id="80ab8-452">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-452">String</span></span>|
|<span data-ttu-id="80ab8-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-453">DATA_TYPE</span></span>|<span data-ttu-id="80ab8-454">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-454">Int16</span></span>|
|<span data-ttu-id="80ab8-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-455">TYPE_NAME</span></span>|<span data-ttu-id="80ab8-456">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-456">String</span></span>|
|<span data-ttu-id="80ab8-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="80ab8-457">PRECISION</span></span>|<span data-ttu-id="80ab8-458">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-458">Int32</span></span>|
|<span data-ttu-id="80ab8-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="80ab8-459">LENGTH</span></span>|<span data-ttu-id="80ab8-460">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-460">Int32</span></span>|
|<span data-ttu-id="80ab8-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="80ab8-461">SCALE</span></span>|<span data-ttu-id="80ab8-462">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-462">Int16</span></span>|
|<span data-ttu-id="80ab8-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="80ab8-463">RADIX</span></span>|<span data-ttu-id="80ab8-464">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-464">Int16</span></span>|
|<span data-ttu-id="80ab8-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="80ab8-465">NULLABLE</span></span>|<span data-ttu-id="80ab8-466">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-466">Int16</span></span>|
|<span data-ttu-id="80ab8-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-467">REMARKS</span></span>|<span data-ttu-id="80ab8-468">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-468">String</span></span>|
|<span data-ttu-id="80ab8-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="80ab8-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="80ab8-470">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="80ab8-471">Процедуры</span><span class="sxs-lookup"><span data-stu-id="80ab8-471">Procedures</span></span>

|<span data-ttu-id="80ab8-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-472">ColumnName</span></span>|<span data-ttu-id="80ab8-473">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="80ab8-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="80ab8-475">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-475">String</span></span>|
|<span data-ttu-id="80ab8-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="80ab8-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="80ab8-477">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-477">String</span></span>|
|<span data-ttu-id="80ab8-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="80ab8-479">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-479">String</span></span>|
|<span data-ttu-id="80ab8-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="80ab8-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="80ab8-481">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-481">Int16</span></span>|
|<span data-ttu-id="80ab8-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="80ab8-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="80ab8-483">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-483">Int16</span></span>|
|<span data-ttu-id="80ab8-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="80ab8-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="80ab8-485">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-485">Int16</span></span>|
|<span data-ttu-id="80ab8-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-486">REMARKS</span></span>|<span data-ttu-id="80ab8-487">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-487">String</span></span>|
|<span data-ttu-id="80ab8-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="80ab8-489">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="80ab8-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="80ab8-490">ProcedureColumns</span></span>

|<span data-ttu-id="80ab8-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-491">ColumnName</span></span>|<span data-ttu-id="80ab8-492">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="80ab8-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="80ab8-494">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-494">String</span></span>|
|<span data-ttu-id="80ab8-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="80ab8-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="80ab8-496">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-496">String</span></span>|
|<span data-ttu-id="80ab8-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="80ab8-498">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-498">String</span></span>|
|<span data-ttu-id="80ab8-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-499">COLUMN_NAME</span></span>|<span data-ttu-id="80ab8-500">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-500">String</span></span>|
|<span data-ttu-id="80ab8-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-501">COLUMN_TYPE</span></span>|<span data-ttu-id="80ab8-502">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-502">Int16</span></span>|
|<span data-ttu-id="80ab8-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-503">DATA_TYPE</span></span>|<span data-ttu-id="80ab8-504">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-504">Int16</span></span>|
|<span data-ttu-id="80ab8-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-505">TYPE_NAME</span></span>|<span data-ttu-id="80ab8-506">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-506">String</span></span>|
|<span data-ttu-id="80ab8-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="80ab8-507">PRECISION</span></span>|<span data-ttu-id="80ab8-508">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-508">Int32</span></span>|
|<span data-ttu-id="80ab8-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="80ab8-509">LENGTH</span></span>|<span data-ttu-id="80ab8-510">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-510">Int32</span></span>|
|<span data-ttu-id="80ab8-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="80ab8-511">SCALE</span></span>|<span data-ttu-id="80ab8-512">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-512">Int16</span></span>|
|<span data-ttu-id="80ab8-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="80ab8-513">RADIX</span></span>|<span data-ttu-id="80ab8-514">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-514">Int16</span></span>|
|<span data-ttu-id="80ab8-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="80ab8-515">NULLABLE</span></span>|<span data-ttu-id="80ab8-516">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-516">Int16</span></span>|
|<span data-ttu-id="80ab8-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-517">REMARKS</span></span>|<span data-ttu-id="80ab8-518">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-518">String</span></span>|
|<span data-ttu-id="80ab8-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="80ab8-519">OVERLOAD</span></span>|<span data-ttu-id="80ab8-520">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-520">Int32</span></span>|
|<span data-ttu-id="80ab8-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="80ab8-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="80ab8-522">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="80ab8-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="80ab8-523">ProcedureParameters</span></span>

|<span data-ttu-id="80ab8-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="80ab8-524">ColumnName</span></span>|<span data-ttu-id="80ab8-525">DataType</span><span class="sxs-lookup"><span data-stu-id="80ab8-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="80ab8-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="80ab8-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="80ab8-527">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-527">String</span></span>|
|<span data-ttu-id="80ab8-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="80ab8-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="80ab8-529">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-529">String</span></span>|
|<span data-ttu-id="80ab8-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="80ab8-531">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-531">String</span></span>|
|<span data-ttu-id="80ab8-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-532">COLUMN_NAME</span></span>|<span data-ttu-id="80ab8-533">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-533">String</span></span>|
|<span data-ttu-id="80ab8-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-534">COLUMN_TYPE</span></span>|<span data-ttu-id="80ab8-535">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-535">Int16</span></span>|
|<span data-ttu-id="80ab8-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-536">DATA_TYPE</span></span>|<span data-ttu-id="80ab8-537">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-537">Int16</span></span>|
|<span data-ttu-id="80ab8-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="80ab8-538">TYPE_NAME</span></span>|<span data-ttu-id="80ab8-539">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-539">String</span></span>|
|<span data-ttu-id="80ab8-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="80ab8-540">COLUMN_SIZE</span></span>|<span data-ttu-id="80ab8-541">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-541">Int32</span></span>|
|<span data-ttu-id="80ab8-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="80ab8-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="80ab8-543">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-543">Int32</span></span>|
|<span data-ttu-id="80ab8-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="80ab8-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="80ab8-545">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-545">Int16</span></span>|
|<span data-ttu-id="80ab8-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="80ab8-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="80ab8-547">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-547">Int16</span></span>|
|<span data-ttu-id="80ab8-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="80ab8-548">NULLABLE</span></span>|<span data-ttu-id="80ab8-549">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-549">Int16</span></span>|
|<span data-ttu-id="80ab8-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="80ab8-550">REMARKS</span></span>|<span data-ttu-id="80ab8-551">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-551">String</span></span>|
|<span data-ttu-id="80ab8-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="80ab8-552">COLUMN_DEF</span></span>|<span data-ttu-id="80ab8-553">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-553">String</span></span>|
|<span data-ttu-id="80ab8-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="80ab8-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="80ab8-555">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-555">Int16</span></span>|
|<span data-ttu-id="80ab8-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="80ab8-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="80ab8-557">Int16</span><span class="sxs-lookup"><span data-stu-id="80ab8-557">Int16</span></span>|
|<span data-ttu-id="80ab8-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="80ab8-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="80ab8-559">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-559">Int32</span></span>|
|<span data-ttu-id="80ab8-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="80ab8-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="80ab8-561">Int32</span><span class="sxs-lookup"><span data-stu-id="80ab8-561">Int32</span></span>|
|<span data-ttu-id="80ab8-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="80ab8-562">IS_NULLABLE</span></span>|<span data-ttu-id="80ab8-563">String</span><span class="sxs-lookup"><span data-stu-id="80ab8-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="80ab8-564">См. также</span><span class="sxs-lookup"><span data-stu-id="80ab8-564">See also</span></span>

- [<span data-ttu-id="80ab8-565">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="80ab8-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

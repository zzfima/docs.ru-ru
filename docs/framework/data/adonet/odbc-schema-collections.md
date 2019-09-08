---
title: Коллекции схемы ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: f0240e99d2420b0956d3c144f837b39e094bb78a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794715"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="d64ee-102">Коллекции схемы ODBC</span><span class="sxs-lookup"><span data-stu-id="d64ee-102">ODBC Schema Collections</span></span>

<span data-ttu-id="d64ee-103">В данном разделе рассматривается поддержка коллекций схем для драйверов ODBC для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="d64ee-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="d64ee-104">Драйвер ODBC для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="d64ee-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="d64ee-105">Драйвер Microsoft SQL Server ODBC поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем:</span><span class="sxs-lookup"><span data-stu-id="d64ee-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="d64ee-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="d64ee-106">Tables</span></span>

- <span data-ttu-id="d64ee-107">Индексы</span><span class="sxs-lookup"><span data-stu-id="d64ee-107">Indexes</span></span>

- <span data-ttu-id="d64ee-108">Столбцы</span><span class="sxs-lookup"><span data-stu-id="d64ee-108">Columns</span></span>

- <span data-ttu-id="d64ee-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="d64ee-109">Procedures</span></span>

- <span data-ttu-id="d64ee-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d64ee-110">ProcedureColumns</span></span>

- <span data-ttu-id="d64ee-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d64ee-111">ProcedureParameters</span></span>

- <span data-ttu-id="d64ee-112">Представления</span><span class="sxs-lookup"><span data-stu-id="d64ee-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="d64ee-113">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="d64ee-113">Tables and Views</span></span>

|<span data-ttu-id="d64ee-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-114">ColumnName</span></span>|<span data-ttu-id="d64ee-115">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="d64ee-116">TABLE_CAT</span></span>|<span data-ttu-id="d64ee-117">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-117">String</span></span>|
|<span data-ttu-id="d64ee-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d64ee-118">TABLE_SCHEM</span></span>|<span data-ttu-id="d64ee-119">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-119">String</span></span>|
|<span data-ttu-id="d64ee-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-120">TABLE_NAME</span></span>|<span data-ttu-id="d64ee-121">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-121">String</span></span>|
|<span data-ttu-id="d64ee-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-122">TABLE_TYPE</span></span>|<span data-ttu-id="d64ee-123">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-123">String</span></span>|
|<span data-ttu-id="d64ee-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-124">REMARKS</span></span>|<span data-ttu-id="d64ee-125">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="d64ee-126">Индексы</span><span class="sxs-lookup"><span data-stu-id="d64ee-126">Indexes</span></span>

|<span data-ttu-id="d64ee-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-127">ColumnName</span></span>|<span data-ttu-id="d64ee-128">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="d64ee-129">TABLE_CAT</span></span>|<span data-ttu-id="d64ee-130">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-130">String</span></span>|
|<span data-ttu-id="d64ee-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d64ee-131">TABLE_SCHEM</span></span>|<span data-ttu-id="d64ee-132">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-132">String</span></span>|
|<span data-ttu-id="d64ee-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-133">TABLE_NAME</span></span>|<span data-ttu-id="d64ee-134">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-134">String</span></span>|
|<span data-ttu-id="d64ee-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d64ee-135">NON_UNIQUE</span></span>|<span data-ttu-id="d64ee-136">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-136">Int16</span></span>|
|<span data-ttu-id="d64ee-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d64ee-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="d64ee-138">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-138">String</span></span>|
|<span data-ttu-id="d64ee-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-139">INDEX_NAME</span></span>|<span data-ttu-id="d64ee-140">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-140">String</span></span>|
|<span data-ttu-id="d64ee-141">ТИП</span><span class="sxs-lookup"><span data-stu-id="d64ee-141">TYPE</span></span>|<span data-ttu-id="d64ee-142">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-142">Int16</span></span>|
|<span data-ttu-id="d64ee-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d64ee-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="d64ee-144">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-144">Int16</span></span>|
|<span data-ttu-id="d64ee-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-145">COLUMN_NAME</span></span>|<span data-ttu-id="d64ee-146">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-146">String</span></span>|
|<span data-ttu-id="d64ee-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="d64ee-147">ASC_OR_DESC</span></span>|<span data-ttu-id="d64ee-148">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-148">String</span></span>|
|<span data-ttu-id="d64ee-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d64ee-149">CARDINALITY</span></span>|<span data-ttu-id="d64ee-150">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-150">Int32</span></span>|
|<span data-ttu-id="d64ee-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="d64ee-151">PAGES</span></span>|<span data-ttu-id="d64ee-152">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-152">Int32</span></span>|
|<span data-ttu-id="d64ee-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d64ee-153">FILTER_CONDITION</span></span>|<span data-ttu-id="d64ee-154">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-154">String</span></span>|
|<span data-ttu-id="d64ee-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d64ee-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d64ee-156">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-156">String</span></span>|
|<span data-ttu-id="d64ee-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="d64ee-158">Byte</span><span class="sxs-lookup"><span data-stu-id="d64ee-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="d64ee-159">Столбцы</span><span class="sxs-lookup"><span data-stu-id="d64ee-159">Columns</span></span>

|<span data-ttu-id="d64ee-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-160">ColumnName</span></span>|<span data-ttu-id="d64ee-161">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="d64ee-162">TABLE_CAT</span></span>|<span data-ttu-id="d64ee-163">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-163">String</span></span>|
|<span data-ttu-id="d64ee-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d64ee-164">TABLE_SCHEM</span></span>|<span data-ttu-id="d64ee-165">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-165">String</span></span>|
|<span data-ttu-id="d64ee-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-166">TABLE_NAME</span></span>|<span data-ttu-id="d64ee-167">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-167">String</span></span>|
|<span data-ttu-id="d64ee-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-168">COLUMN_NAME</span></span>|<span data-ttu-id="d64ee-169">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-169">String</span></span>|
|<span data-ttu-id="d64ee-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-170">DATA_TYPE</span></span>|<span data-ttu-id="d64ee-171">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-171">Int16</span></span>|
|<span data-ttu-id="d64ee-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-172">TYPE_NAME</span></span>|<span data-ttu-id="d64ee-173">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-173">String</span></span>|
|<span data-ttu-id="d64ee-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d64ee-174">COLUMN_SIZE</span></span>|<span data-ttu-id="d64ee-175">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-175">Int32</span></span>|
|<span data-ttu-id="d64ee-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d64ee-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="d64ee-177">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-177">Int32</span></span>|
|<span data-ttu-id="d64ee-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d64ee-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d64ee-179">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-179">Int16</span></span>|
|<span data-ttu-id="d64ee-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d64ee-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d64ee-181">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-181">Int16</span></span>|
|<span data-ttu-id="d64ee-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d64ee-182">NULLABLE</span></span>|<span data-ttu-id="d64ee-183">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-183">Int16</span></span>|
|<span data-ttu-id="d64ee-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-184">REMARKS</span></span>|<span data-ttu-id="d64ee-185">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-185">String</span></span>|
|<span data-ttu-id="d64ee-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d64ee-186">COLUMN_DEF</span></span>|<span data-ttu-id="d64ee-187">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-187">String</span></span>|
|<span data-ttu-id="d64ee-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d64ee-189">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-189">Int16</span></span>|
|<span data-ttu-id="d64ee-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d64ee-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d64ee-191">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-191">Int16</span></span>|
|<span data-ttu-id="d64ee-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d64ee-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d64ee-193">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-193">Int32</span></span>|
|<span data-ttu-id="d64ee-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d64ee-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="d64ee-195">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-195">Int32</span></span>|
|<span data-ttu-id="d64ee-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d64ee-196">IS_NULLABLE</span></span>|<span data-ttu-id="d64ee-197">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-197">String</span></span>|
|<span data-ttu-id="d64ee-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d64ee-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="d64ee-199">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-199">String</span></span>|
|<span data-ttu-id="d64ee-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d64ee-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d64ee-201">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-201">String</span></span>|
|<span data-ttu-id="d64ee-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="d64ee-203">Byte</span><span class="sxs-lookup"><span data-stu-id="d64ee-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="d64ee-204">Процедуры</span><span class="sxs-lookup"><span data-stu-id="d64ee-204">Procedures</span></span>

|<span data-ttu-id="d64ee-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-205">ColumnName</span></span>|<span data-ttu-id="d64ee-206">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d64ee-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="d64ee-208">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-208">String</span></span>|
|<span data-ttu-id="d64ee-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d64ee-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d64ee-210">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-210">String</span></span>|
|<span data-ttu-id="d64ee-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="d64ee-212">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-212">String</span></span>|
|<span data-ttu-id="d64ee-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d64ee-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="d64ee-214">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-214">Int32</span></span>|
|<span data-ttu-id="d64ee-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d64ee-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="d64ee-216">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-216">Int32</span></span>|
|<span data-ttu-id="d64ee-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="d64ee-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="d64ee-218">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-218">Int32</span></span>|
|<span data-ttu-id="d64ee-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-219">REMARKS</span></span>|<span data-ttu-id="d64ee-220">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-220">String</span></span>|
|<span data-ttu-id="d64ee-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d64ee-222">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="d64ee-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d64ee-223">ProcedureColumns</span></span>

|<span data-ttu-id="d64ee-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-224">ColumnName</span></span>|<span data-ttu-id="d64ee-225">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d64ee-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="d64ee-227">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-227">String</span></span>|
|<span data-ttu-id="d64ee-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d64ee-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d64ee-229">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-229">String</span></span>|
|<span data-ttu-id="d64ee-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="d64ee-231">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-231">String</span></span>|
|<span data-ttu-id="d64ee-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-232">COLUMN_NAME</span></span>|<span data-ttu-id="d64ee-233">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-233">String</span></span>|
|<span data-ttu-id="d64ee-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-234">COLUMN_TYPE</span></span>|<span data-ttu-id="d64ee-235">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-235">Int16</span></span>|
|<span data-ttu-id="d64ee-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-236">DATA_TYPE</span></span>|<span data-ttu-id="d64ee-237">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-237">Int16</span></span>|
|<span data-ttu-id="d64ee-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-238">TYPE_NAME</span></span>|<span data-ttu-id="d64ee-239">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-239">String</span></span>|
|<span data-ttu-id="d64ee-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d64ee-240">COLUMN_SIZE</span></span>|<span data-ttu-id="d64ee-241">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-241">Int32</span></span>|
|<span data-ttu-id="d64ee-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d64ee-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="d64ee-243">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-243">Int32</span></span>|
|<span data-ttu-id="d64ee-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d64ee-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d64ee-245">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-245">Int16</span></span>|
|<span data-ttu-id="d64ee-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d64ee-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d64ee-247">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-247">Int16</span></span>|
|<span data-ttu-id="d64ee-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d64ee-248">NULLABLE</span></span>|<span data-ttu-id="d64ee-249">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-249">Int16</span></span>|
|<span data-ttu-id="d64ee-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-250">REMARKS</span></span>|<span data-ttu-id="d64ee-251">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-251">String</span></span>|
|<span data-ttu-id="d64ee-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d64ee-252">COLUMN_DEF</span></span>|<span data-ttu-id="d64ee-253">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-253">String</span></span>|
|<span data-ttu-id="d64ee-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d64ee-255">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-255">Int16</span></span>|
|<span data-ttu-id="d64ee-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d64ee-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d64ee-257">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-257">Int16</span></span>|
|<span data-ttu-id="d64ee-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d64ee-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d64ee-259">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-259">Int32</span></span>|
|<span data-ttu-id="d64ee-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d64ee-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="d64ee-261">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-261">Int32</span></span>|
|<span data-ttu-id="d64ee-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d64ee-262">IS_NULLABLE</span></span>|<span data-ttu-id="d64ee-263">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-263">String</span></span>|
|<span data-ttu-id="d64ee-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d64ee-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="d64ee-265">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-265">String</span></span>|
|<span data-ttu-id="d64ee-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d64ee-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d64ee-267">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-267">String</span></span>|
|<span data-ttu-id="d64ee-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="d64ee-269">Byte</span><span class="sxs-lookup"><span data-stu-id="d64ee-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="d64ee-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d64ee-270">ProcedureParameters</span></span>

|<span data-ttu-id="d64ee-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-271">ColumnName</span></span>|<span data-ttu-id="d64ee-272">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d64ee-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="d64ee-274">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-274">String</span></span>|
|<span data-ttu-id="d64ee-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d64ee-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d64ee-276">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-276">String</span></span>|
|<span data-ttu-id="d64ee-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="d64ee-278">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-278">String</span></span>|
|<span data-ttu-id="d64ee-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-279">COLUMN_NAME</span></span>|<span data-ttu-id="d64ee-280">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-280">String</span></span>|
|<span data-ttu-id="d64ee-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-281">COLUMN_TYPE</span></span>|<span data-ttu-id="d64ee-282">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-282">Int16</span></span>|
|<span data-ttu-id="d64ee-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-283">DATA_TYPE</span></span>|<span data-ttu-id="d64ee-284">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-284">Int16</span></span>|
|<span data-ttu-id="d64ee-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-285">TYPE_NAME</span></span>|<span data-ttu-id="d64ee-286">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-286">String</span></span>|
|<span data-ttu-id="d64ee-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d64ee-287">COLUMN_SIZE</span></span>|<span data-ttu-id="d64ee-288">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-288">Int32</span></span>|
|<span data-ttu-id="d64ee-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d64ee-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="d64ee-290">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-290">Int32</span></span>|
|<span data-ttu-id="d64ee-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d64ee-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d64ee-292">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-292">Int16</span></span>|
|<span data-ttu-id="d64ee-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d64ee-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d64ee-294">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-294">Int16</span></span>|
|<span data-ttu-id="d64ee-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d64ee-295">NULLABLE</span></span>|<span data-ttu-id="d64ee-296">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-296">Int16</span></span>|
|<span data-ttu-id="d64ee-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-297">REMARKS</span></span>|<span data-ttu-id="d64ee-298">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-298">String</span></span>|
|<span data-ttu-id="d64ee-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d64ee-299">COLUMN_DEF</span></span>|<span data-ttu-id="d64ee-300">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-300">String</span></span>|
|<span data-ttu-id="d64ee-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d64ee-302">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-302">Int16</span></span>|
|<span data-ttu-id="d64ee-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d64ee-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d64ee-304">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-304">Int16</span></span>|
|<span data-ttu-id="d64ee-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d64ee-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d64ee-306">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-306">Int32</span></span>|
|<span data-ttu-id="d64ee-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d64ee-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="d64ee-308">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-308">Int32</span></span>|
|<span data-ttu-id="d64ee-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d64ee-309">IS_NULLABLE</span></span>|<span data-ttu-id="d64ee-310">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-310">String</span></span>|
|<span data-ttu-id="d64ee-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d64ee-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="d64ee-312">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-312">String</span></span>|
|<span data-ttu-id="d64ee-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d64ee-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="d64ee-314">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-314">String</span></span>|
|<span data-ttu-id="d64ee-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="d64ee-316">Byte</span><span class="sxs-lookup"><span data-stu-id="d64ee-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="d64ee-317">Драйвер ODBC для Oracle (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="d64ee-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="d64ee-318">Драйвер Microsoft SQL Server Oracle ODBC поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем:</span><span class="sxs-lookup"><span data-stu-id="d64ee-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="d64ee-319">Таблицы</span><span class="sxs-lookup"><span data-stu-id="d64ee-319">Tables</span></span>

- <span data-ttu-id="d64ee-320">Столбцы</span><span class="sxs-lookup"><span data-stu-id="d64ee-320">Columns</span></span>

- <span data-ttu-id="d64ee-321">Процедуры</span><span class="sxs-lookup"><span data-stu-id="d64ee-321">Procedures</span></span>

- <span data-ttu-id="d64ee-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d64ee-322">ProcedureColumns</span></span>

- <span data-ttu-id="d64ee-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d64ee-323">ProcedureParameters</span></span>

- <span data-ttu-id="d64ee-324">Представления</span><span class="sxs-lookup"><span data-stu-id="d64ee-324">Views</span></span>

- <span data-ttu-id="d64ee-325">Индексы</span><span class="sxs-lookup"><span data-stu-id="d64ee-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="d64ee-326">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="d64ee-326">Tables and Views</span></span>

|<span data-ttu-id="d64ee-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-327">ColumnName</span></span>|<span data-ttu-id="d64ee-328">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d64ee-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d64ee-330">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-330">String</span></span>|
|<span data-ttu-id="d64ee-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d64ee-331">TABLE_OWNER</span></span>|<span data-ttu-id="d64ee-332">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-332">String</span></span>|
|<span data-ttu-id="d64ee-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-333">TABLE_NAME</span></span>|<span data-ttu-id="d64ee-334">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-334">String</span></span>|
|<span data-ttu-id="d64ee-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-335">TABLE_TYPE</span></span>|<span data-ttu-id="d64ee-336">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-336">String</span></span>|
|<span data-ttu-id="d64ee-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-337">REMARKS</span></span>|<span data-ttu-id="d64ee-338">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="d64ee-339">Столбцы</span><span class="sxs-lookup"><span data-stu-id="d64ee-339">Columns</span></span>

|<span data-ttu-id="d64ee-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-340">ColumnName</span></span>|<span data-ttu-id="d64ee-341">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d64ee-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d64ee-343">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-343">String</span></span>|
|<span data-ttu-id="d64ee-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d64ee-344">TABLE_OWNER</span></span>|<span data-ttu-id="d64ee-345">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-345">String</span></span>|
|<span data-ttu-id="d64ee-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-346">TABLE_NAME</span></span>|<span data-ttu-id="d64ee-347">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-347">String</span></span>|
|<span data-ttu-id="d64ee-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-348">COLUMN_NAME</span></span>|<span data-ttu-id="d64ee-349">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-349">String</span></span>|
|<span data-ttu-id="d64ee-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-350">DATA_TYPE</span></span>|<span data-ttu-id="d64ee-351">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-351">Int16</span></span>|
|<span data-ttu-id="d64ee-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-352">TYPE_NAME</span></span>|<span data-ttu-id="d64ee-353">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-353">String</span></span>|
|<span data-ttu-id="d64ee-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d64ee-354">PRECISION</span></span>|<span data-ttu-id="d64ee-355">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-355">Int32</span></span>|
|<span data-ttu-id="d64ee-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d64ee-356">LENGTH</span></span>|<span data-ttu-id="d64ee-357">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-357">Int32</span></span>|
|<span data-ttu-id="d64ee-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="d64ee-358">SCALE</span></span>|<span data-ttu-id="d64ee-359">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-359">Int16</span></span>|
|<span data-ttu-id="d64ee-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="d64ee-360">RADIX</span></span>|<span data-ttu-id="d64ee-361">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-361">Int16</span></span>|
|<span data-ttu-id="d64ee-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d64ee-362">NULLABLE</span></span>|<span data-ttu-id="d64ee-363">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-363">Int16</span></span>|
|<span data-ttu-id="d64ee-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-364">REMARKS</span></span>|<span data-ttu-id="d64ee-365">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-365">String</span></span>|
|<span data-ttu-id="d64ee-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d64ee-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="d64ee-367">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="d64ee-368">Процедуры</span><span class="sxs-lookup"><span data-stu-id="d64ee-368">Procedures</span></span>

|<span data-ttu-id="d64ee-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-369">ColumnName</span></span>|<span data-ttu-id="d64ee-370">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d64ee-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d64ee-372">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-372">String</span></span>|
|<span data-ttu-id="d64ee-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d64ee-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d64ee-374">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-374">String</span></span>|
|<span data-ttu-id="d64ee-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="d64ee-376">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-376">String</span></span>|
|<span data-ttu-id="d64ee-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d64ee-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="d64ee-378">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-378">Int16</span></span>|
|<span data-ttu-id="d64ee-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d64ee-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="d64ee-380">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-380">Int16</span></span>|
|<span data-ttu-id="d64ee-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="d64ee-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="d64ee-382">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-382">Int16</span></span>|
|<span data-ttu-id="d64ee-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-383">REMARKS</span></span>|<span data-ttu-id="d64ee-384">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-384">String</span></span>|
|<span data-ttu-id="d64ee-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d64ee-386">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="d64ee-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d64ee-387">ProcedureColumns</span></span>

|<span data-ttu-id="d64ee-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-388">ColumnName</span></span>|<span data-ttu-id="d64ee-389">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d64ee-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d64ee-391">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-391">String</span></span>|
|<span data-ttu-id="d64ee-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d64ee-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d64ee-393">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-393">String</span></span>|
|<span data-ttu-id="d64ee-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="d64ee-395">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-395">String</span></span>|
|<span data-ttu-id="d64ee-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-396">COLUMN_NAME</span></span>|<span data-ttu-id="d64ee-397">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-397">String</span></span>|
|<span data-ttu-id="d64ee-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-398">COLUMN_TYPE</span></span>|<span data-ttu-id="d64ee-399">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-399">Int16</span></span>|
|<span data-ttu-id="d64ee-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-400">DATA_TYPE</span></span>|<span data-ttu-id="d64ee-401">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-401">Int16</span></span>|
|<span data-ttu-id="d64ee-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-402">TYPE_NAME</span></span>|<span data-ttu-id="d64ee-403">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-403">String</span></span>|
|<span data-ttu-id="d64ee-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d64ee-404">PRECISION</span></span>|<span data-ttu-id="d64ee-405">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-405">Int32</span></span>|
|<span data-ttu-id="d64ee-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d64ee-406">LENGTH</span></span>|<span data-ttu-id="d64ee-407">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-407">Int32</span></span>|
|<span data-ttu-id="d64ee-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="d64ee-408">SCALE</span></span>|<span data-ttu-id="d64ee-409">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-409">Int16</span></span>|
|<span data-ttu-id="d64ee-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="d64ee-410">RADIX</span></span>|<span data-ttu-id="d64ee-411">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-411">Int16</span></span>|
|<span data-ttu-id="d64ee-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d64ee-412">NULLABLE</span></span>|<span data-ttu-id="d64ee-413">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-413">Int16</span></span>|
|<span data-ttu-id="d64ee-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-414">REMARKS</span></span>|<span data-ttu-id="d64ee-415">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-415">String</span></span>|
|<span data-ttu-id="d64ee-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="d64ee-416">OVERLOAD</span></span>|<span data-ttu-id="d64ee-417">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-417">Int32</span></span>|
|<span data-ttu-id="d64ee-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d64ee-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="d64ee-419">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="d64ee-420">Драйвер ODBC для Jet (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="d64ee-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="d64ee-421">Драйвер ODBC для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="d64ee-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="d64ee-422">Таблицы</span><span class="sxs-lookup"><span data-stu-id="d64ee-422">Tables</span></span>

- <span data-ttu-id="d64ee-423">Индексы</span><span class="sxs-lookup"><span data-stu-id="d64ee-423">Indexes</span></span>

- <span data-ttu-id="d64ee-424">Столбцы</span><span class="sxs-lookup"><span data-stu-id="d64ee-424">Columns</span></span>

- <span data-ttu-id="d64ee-425">Процедуры</span><span class="sxs-lookup"><span data-stu-id="d64ee-425">Procedures</span></span>

- <span data-ttu-id="d64ee-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d64ee-426">ProcedureColumns</span></span>

- <span data-ttu-id="d64ee-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d64ee-427">ProcedureParameters</span></span>

- <span data-ttu-id="d64ee-428">Представления</span><span class="sxs-lookup"><span data-stu-id="d64ee-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="d64ee-429">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="d64ee-429">Tables and Views</span></span>

|<span data-ttu-id="d64ee-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-430">ColumnName</span></span>|<span data-ttu-id="d64ee-431">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d64ee-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d64ee-433">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-433">String</span></span>|
|<span data-ttu-id="d64ee-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d64ee-434">TABLE_OWNER</span></span>|<span data-ttu-id="d64ee-435">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-435">String</span></span>|
|<span data-ttu-id="d64ee-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-436">TABLE_NAME</span></span>|<span data-ttu-id="d64ee-437">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-437">String</span></span>|
|<span data-ttu-id="d64ee-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-438">TABLE_TYPE</span></span>|<span data-ttu-id="d64ee-439">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-439">String</span></span>|
|<span data-ttu-id="d64ee-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-440">REMARKS</span></span>|<span data-ttu-id="d64ee-441">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="d64ee-442">Столбцы</span><span class="sxs-lookup"><span data-stu-id="d64ee-442">Columns</span></span>

|<span data-ttu-id="d64ee-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-443">ColumnName</span></span>|<span data-ttu-id="d64ee-444">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d64ee-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="d64ee-446">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-446">String</span></span>|
|<span data-ttu-id="d64ee-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d64ee-447">TABLE_OWNER</span></span>|<span data-ttu-id="d64ee-448">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-448">String</span></span>|
|<span data-ttu-id="d64ee-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-449">TABLE_NAME</span></span>|<span data-ttu-id="d64ee-450">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-450">String</span></span>|
|<span data-ttu-id="d64ee-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-451">COLUMN_NAME</span></span>|<span data-ttu-id="d64ee-452">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-452">String</span></span>|
|<span data-ttu-id="d64ee-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-453">DATA_TYPE</span></span>|<span data-ttu-id="d64ee-454">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-454">Int16</span></span>|
|<span data-ttu-id="d64ee-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-455">TYPE_NAME</span></span>|<span data-ttu-id="d64ee-456">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-456">String</span></span>|
|<span data-ttu-id="d64ee-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d64ee-457">PRECISION</span></span>|<span data-ttu-id="d64ee-458">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-458">Int32</span></span>|
|<span data-ttu-id="d64ee-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d64ee-459">LENGTH</span></span>|<span data-ttu-id="d64ee-460">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-460">Int32</span></span>|
|<span data-ttu-id="d64ee-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="d64ee-461">SCALE</span></span>|<span data-ttu-id="d64ee-462">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-462">Int16</span></span>|
|<span data-ttu-id="d64ee-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="d64ee-463">RADIX</span></span>|<span data-ttu-id="d64ee-464">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-464">Int16</span></span>|
|<span data-ttu-id="d64ee-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d64ee-465">NULLABLE</span></span>|<span data-ttu-id="d64ee-466">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-466">Int16</span></span>|
|<span data-ttu-id="d64ee-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-467">REMARKS</span></span>|<span data-ttu-id="d64ee-468">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-468">String</span></span>|
|<span data-ttu-id="d64ee-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d64ee-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="d64ee-470">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="d64ee-471">Процедуры</span><span class="sxs-lookup"><span data-stu-id="d64ee-471">Procedures</span></span>

|<span data-ttu-id="d64ee-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-472">ColumnName</span></span>|<span data-ttu-id="d64ee-473">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d64ee-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d64ee-475">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-475">String</span></span>|
|<span data-ttu-id="d64ee-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d64ee-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d64ee-477">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-477">String</span></span>|
|<span data-ttu-id="d64ee-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="d64ee-479">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-479">String</span></span>|
|<span data-ttu-id="d64ee-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d64ee-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="d64ee-481">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-481">Int16</span></span>|
|<span data-ttu-id="d64ee-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="d64ee-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="d64ee-483">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-483">Int16</span></span>|
|<span data-ttu-id="d64ee-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="d64ee-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="d64ee-485">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-485">Int16</span></span>|
|<span data-ttu-id="d64ee-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-486">REMARKS</span></span>|<span data-ttu-id="d64ee-487">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-487">String</span></span>|
|<span data-ttu-id="d64ee-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d64ee-489">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="d64ee-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d64ee-490">ProcedureColumns</span></span>

|<span data-ttu-id="d64ee-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-491">ColumnName</span></span>|<span data-ttu-id="d64ee-492">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="d64ee-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="d64ee-494">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-494">String</span></span>|
|<span data-ttu-id="d64ee-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="d64ee-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="d64ee-496">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-496">String</span></span>|
|<span data-ttu-id="d64ee-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="d64ee-498">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-498">String</span></span>|
|<span data-ttu-id="d64ee-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-499">COLUMN_NAME</span></span>|<span data-ttu-id="d64ee-500">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-500">String</span></span>|
|<span data-ttu-id="d64ee-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-501">COLUMN_TYPE</span></span>|<span data-ttu-id="d64ee-502">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-502">Int16</span></span>|
|<span data-ttu-id="d64ee-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-503">DATA_TYPE</span></span>|<span data-ttu-id="d64ee-504">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-504">Int16</span></span>|
|<span data-ttu-id="d64ee-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-505">TYPE_NAME</span></span>|<span data-ttu-id="d64ee-506">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-506">String</span></span>|
|<span data-ttu-id="d64ee-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="d64ee-507">PRECISION</span></span>|<span data-ttu-id="d64ee-508">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-508">Int32</span></span>|
|<span data-ttu-id="d64ee-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="d64ee-509">LENGTH</span></span>|<span data-ttu-id="d64ee-510">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-510">Int32</span></span>|
|<span data-ttu-id="d64ee-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="d64ee-511">SCALE</span></span>|<span data-ttu-id="d64ee-512">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-512">Int16</span></span>|
|<span data-ttu-id="d64ee-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="d64ee-513">RADIX</span></span>|<span data-ttu-id="d64ee-514">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-514">Int16</span></span>|
|<span data-ttu-id="d64ee-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d64ee-515">NULLABLE</span></span>|<span data-ttu-id="d64ee-516">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-516">Int16</span></span>|
|<span data-ttu-id="d64ee-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-517">REMARKS</span></span>|<span data-ttu-id="d64ee-518">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-518">String</span></span>|
|<span data-ttu-id="d64ee-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="d64ee-519">OVERLOAD</span></span>|<span data-ttu-id="d64ee-520">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-520">Int32</span></span>|
|<span data-ttu-id="d64ee-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d64ee-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="d64ee-522">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="d64ee-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d64ee-523">ProcedureParameters</span></span>

|<span data-ttu-id="d64ee-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="d64ee-524">ColumnName</span></span>|<span data-ttu-id="d64ee-525">DataType</span><span class="sxs-lookup"><span data-stu-id="d64ee-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="d64ee-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="d64ee-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="d64ee-527">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-527">String</span></span>|
|<span data-ttu-id="d64ee-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="d64ee-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="d64ee-529">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-529">String</span></span>|
|<span data-ttu-id="d64ee-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="d64ee-531">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-531">String</span></span>|
|<span data-ttu-id="d64ee-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-532">COLUMN_NAME</span></span>|<span data-ttu-id="d64ee-533">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-533">String</span></span>|
|<span data-ttu-id="d64ee-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-534">COLUMN_TYPE</span></span>|<span data-ttu-id="d64ee-535">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-535">Int16</span></span>|
|<span data-ttu-id="d64ee-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-536">DATA_TYPE</span></span>|<span data-ttu-id="d64ee-537">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-537">Int16</span></span>|
|<span data-ttu-id="d64ee-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d64ee-538">TYPE_NAME</span></span>|<span data-ttu-id="d64ee-539">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-539">String</span></span>|
|<span data-ttu-id="d64ee-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="d64ee-540">COLUMN_SIZE</span></span>|<span data-ttu-id="d64ee-541">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-541">Int32</span></span>|
|<span data-ttu-id="d64ee-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d64ee-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="d64ee-543">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-543">Int32</span></span>|
|<span data-ttu-id="d64ee-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="d64ee-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="d64ee-545">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-545">Int16</span></span>|
|<span data-ttu-id="d64ee-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="d64ee-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="d64ee-547">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-547">Int16</span></span>|
|<span data-ttu-id="d64ee-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d64ee-548">NULLABLE</span></span>|<span data-ttu-id="d64ee-549">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-549">Int16</span></span>|
|<span data-ttu-id="d64ee-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="d64ee-550">REMARKS</span></span>|<span data-ttu-id="d64ee-551">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-551">String</span></span>|
|<span data-ttu-id="d64ee-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="d64ee-552">COLUMN_DEF</span></span>|<span data-ttu-id="d64ee-553">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-553">String</span></span>|
|<span data-ttu-id="d64ee-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d64ee-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="d64ee-555">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-555">Int16</span></span>|
|<span data-ttu-id="d64ee-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="d64ee-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="d64ee-557">Int16</span><span class="sxs-lookup"><span data-stu-id="d64ee-557">Int16</span></span>|
|<span data-ttu-id="d64ee-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d64ee-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="d64ee-559">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-559">Int32</span></span>|
|<span data-ttu-id="d64ee-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d64ee-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="d64ee-561">Int32</span><span class="sxs-lookup"><span data-stu-id="d64ee-561">Int32</span></span>|
|<span data-ttu-id="d64ee-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d64ee-562">IS_NULLABLE</span></span>|<span data-ttu-id="d64ee-563">String</span><span class="sxs-lookup"><span data-stu-id="d64ee-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="d64ee-564">См. также</span><span class="sxs-lookup"><span data-stu-id="d64ee-564">See also</span></span>

- [<span data-ttu-id="d64ee-565">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d64ee-565">ADO.NET Overview</span></span>](ado-net-overview.md)

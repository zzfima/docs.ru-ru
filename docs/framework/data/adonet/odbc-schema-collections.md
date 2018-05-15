---
title: Коллекции схемы ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: 36d0859b897bfcea33803c219ade14722ed90421
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="39847-102">Коллекции схемы ODBC</span><span class="sxs-lookup"><span data-stu-id="39847-102">ODBC Schema Collections</span></span>
<span data-ttu-id="39847-103">В данном разделе рассматривается поддержка коллекций схем для драйверов ODBC для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="39847-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="39847-104">Драйвер ODBC для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="39847-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="39847-105">Драйвер ODBC для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем.</span><span class="sxs-lookup"><span data-stu-id="39847-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="39847-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="39847-106">Tables</span></span>  
  
-   <span data-ttu-id="39847-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="39847-107">Indexes</span></span>  
  
-   <span data-ttu-id="39847-108">Столбцы</span><span class="sxs-lookup"><span data-stu-id="39847-108">Columns</span></span>  
  
-   <span data-ttu-id="39847-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="39847-109">Procedures</span></span>  
  
-   <span data-ttu-id="39847-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="39847-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="39847-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="39847-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="39847-112">Представления</span><span class="sxs-lookup"><span data-stu-id="39847-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="39847-113">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="39847-113">Tables and Views</span></span>  
  
|<span data-ttu-id="39847-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-114">ColumnName</span></span>|<span data-ttu-id="39847-115">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="39847-116">TABLE_CAT</span></span>|<span data-ttu-id="39847-117">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-117">String</span></span>|  
|<span data-ttu-id="39847-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="39847-118">TABLE_SCHEM</span></span>|<span data-ttu-id="39847-119">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-119">String</span></span>|  
|<span data-ttu-id="39847-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-120">TABLE_NAME</span></span>|<span data-ttu-id="39847-121">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-121">String</span></span>|  
|<span data-ttu-id="39847-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-122">TABLE_TYPE</span></span>|<span data-ttu-id="39847-123">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-123">String</span></span>|  
|<span data-ttu-id="39847-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-124">REMARKS</span></span>|<span data-ttu-id="39847-125">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="39847-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="39847-126">Indexes</span></span>  
  
|<span data-ttu-id="39847-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-127">ColumnName</span></span>|<span data-ttu-id="39847-128">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="39847-129">TABLE_CAT</span></span>|<span data-ttu-id="39847-130">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-130">String</span></span>|  
|<span data-ttu-id="39847-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="39847-131">TABLE_SCHEM</span></span>|<span data-ttu-id="39847-132">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-132">String</span></span>|  
|<span data-ttu-id="39847-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-133">TABLE_NAME</span></span>|<span data-ttu-id="39847-134">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-134">String</span></span>|  
|<span data-ttu-id="39847-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="39847-135">NON_UNIQUE</span></span>|<span data-ttu-id="39847-136">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-136">Int16</span></span>|  
|<span data-ttu-id="39847-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="39847-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="39847-138">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-138">String</span></span>|  
|<span data-ttu-id="39847-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-139">INDEX_NAME</span></span>|<span data-ttu-id="39847-140">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-140">String</span></span>|  
|<span data-ttu-id="39847-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-141">TYPE</span></span>|<span data-ttu-id="39847-142">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-142">Int16</span></span>|  
|<span data-ttu-id="39847-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="39847-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="39847-144">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-144">Int16</span></span>|  
|<span data-ttu-id="39847-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-145">COLUMN_NAME</span></span>|<span data-ttu-id="39847-146">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-146">String</span></span>|  
|<span data-ttu-id="39847-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="39847-147">ASC_OR_DESC</span></span>|<span data-ttu-id="39847-148">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-148">String</span></span>|  
|<span data-ttu-id="39847-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="39847-149">CARDINATLITY</span></span>|<span data-ttu-id="39847-150">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-150">Int32</span></span>|  
|<span data-ttu-id="39847-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="39847-151">PAGES</span></span>|<span data-ttu-id="39847-152">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-152">Int32</span></span>|  
|<span data-ttu-id="39847-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="39847-153">FILTER_CONDITION</span></span>|<span data-ttu-id="39847-154">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-154">String</span></span>|  
|<span data-ttu-id="39847-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39847-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="39847-156">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-156">String</span></span>|  
|<span data-ttu-id="39847-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="39847-158">Byte</span><span class="sxs-lookup"><span data-stu-id="39847-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="39847-159">Столбцы</span><span class="sxs-lookup"><span data-stu-id="39847-159">Columns</span></span>  
  
|<span data-ttu-id="39847-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-160">ColumnName</span></span>|<span data-ttu-id="39847-161">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="39847-162">TABLE_CAT</span></span>|<span data-ttu-id="39847-163">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-163">String</span></span>|  
|<span data-ttu-id="39847-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="39847-164">TABLE_SCHEM</span></span>|<span data-ttu-id="39847-165">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-165">String</span></span>|  
|<span data-ttu-id="39847-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-166">TABLE_NAME</span></span>|<span data-ttu-id="39847-167">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-167">String</span></span>|  
|<span data-ttu-id="39847-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-168">COLUMN_NAME</span></span>|<span data-ttu-id="39847-169">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-169">String</span></span>|  
|<span data-ttu-id="39847-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-170">DATA_TYPE</span></span>|<span data-ttu-id="39847-171">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-171">Int16</span></span>|  
|<span data-ttu-id="39847-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-172">TYPE_NAME</span></span>|<span data-ttu-id="39847-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-173">String</span></span>|  
|<span data-ttu-id="39847-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="39847-174">COLUMN_SIZE</span></span>|<span data-ttu-id="39847-175">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-175">Int32</span></span>|  
|<span data-ttu-id="39847-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="39847-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="39847-177">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-177">Int32</span></span>|  
|<span data-ttu-id="39847-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="39847-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="39847-179">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-179">Int16</span></span>|  
|<span data-ttu-id="39847-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="39847-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="39847-181">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-181">Int16</span></span>|  
|<span data-ttu-id="39847-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="39847-182">NULLABLE</span></span>|<span data-ttu-id="39847-183">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-183">Int16</span></span>|  
|<span data-ttu-id="39847-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-184">REMARKS</span></span>|<span data-ttu-id="39847-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-185">String</span></span>|  
|<span data-ttu-id="39847-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="39847-186">COLUMN_DEF</span></span>|<span data-ttu-id="39847-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-187">String</span></span>|  
|<span data-ttu-id="39847-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="39847-189">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-189">Int16</span></span>|  
|<span data-ttu-id="39847-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="39847-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="39847-191">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-191">Int16</span></span>|  
|<span data-ttu-id="39847-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="39847-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="39847-193">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-193">Int32</span></span>|  
|<span data-ttu-id="39847-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="39847-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="39847-195">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-195">Int32</span></span>|  
|<span data-ttu-id="39847-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="39847-196">IS_NULLABLE</span></span>|<span data-ttu-id="39847-197">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-197">String</span></span>|  
|<span data-ttu-id="39847-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39847-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="39847-199">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-199">String</span></span>|  
|<span data-ttu-id="39847-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39847-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="39847-201">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-201">String</span></span>|  
|<span data-ttu-id="39847-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="39847-203">Byte</span><span class="sxs-lookup"><span data-stu-id="39847-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="39847-204">Процедуры</span><span class="sxs-lookup"><span data-stu-id="39847-204">Procedures</span></span>  
  
|<span data-ttu-id="39847-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-205">ColumnName</span></span>|<span data-ttu-id="39847-206">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="39847-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="39847-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-208">String</span></span>|  
|<span data-ttu-id="39847-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="39847-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="39847-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-210">String</span></span>|  
|<span data-ttu-id="39847-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="39847-212">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-212">String</span></span>|  
|<span data-ttu-id="39847-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="39847-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="39847-214">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-214">Int32</span></span>|  
|<span data-ttu-id="39847-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="39847-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="39847-216">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-216">Int32</span></span>|  
|<span data-ttu-id="39847-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="39847-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="39847-218">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-218">Int32</span></span>|  
|<span data-ttu-id="39847-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-219">REMARKS</span></span>|<span data-ttu-id="39847-220">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-220">String</span></span>|  
|<span data-ttu-id="39847-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="39847-222">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="39847-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="39847-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="39847-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-224">ColumnName</span></span>|<span data-ttu-id="39847-225">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="39847-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="39847-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-227">String</span></span>|  
|<span data-ttu-id="39847-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="39847-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="39847-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-229">String</span></span>|  
|<span data-ttu-id="39847-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="39847-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-231">String</span></span>|  
|<span data-ttu-id="39847-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-232">COLUMN_NAME</span></span>|<span data-ttu-id="39847-233">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-233">String</span></span>|  
|<span data-ttu-id="39847-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-234">COLUMN_TYPE</span></span>|<span data-ttu-id="39847-235">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-235">Int16</span></span>|  
|<span data-ttu-id="39847-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-236">DATA_TYPE</span></span>|<span data-ttu-id="39847-237">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-237">Int16</span></span>|  
|<span data-ttu-id="39847-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-238">TYPE_NAME</span></span>|<span data-ttu-id="39847-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-239">String</span></span>|  
|<span data-ttu-id="39847-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="39847-240">COLUMN_SIZE</span></span>|<span data-ttu-id="39847-241">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-241">Int32</span></span>|  
|<span data-ttu-id="39847-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="39847-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="39847-243">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-243">Int32</span></span>|  
|<span data-ttu-id="39847-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="39847-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="39847-245">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-245">Int16</span></span>|  
|<span data-ttu-id="39847-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="39847-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="39847-247">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-247">Int16</span></span>|  
|<span data-ttu-id="39847-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="39847-248">NULLABLE</span></span>|<span data-ttu-id="39847-249">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-249">Int16</span></span>|  
|<span data-ttu-id="39847-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-250">REMARKS</span></span>|<span data-ttu-id="39847-251">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-251">String</span></span>|  
|<span data-ttu-id="39847-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="39847-252">COLUMN_DEF</span></span>|<span data-ttu-id="39847-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-253">String</span></span>|  
|<span data-ttu-id="39847-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="39847-255">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-255">Int16</span></span>|  
|<span data-ttu-id="39847-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="39847-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="39847-257">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-257">Int16</span></span>|  
|<span data-ttu-id="39847-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="39847-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="39847-259">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-259">Int32</span></span>|  
|<span data-ttu-id="39847-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="39847-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="39847-261">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-261">Int32</span></span>|  
|<span data-ttu-id="39847-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="39847-262">IS_NULLABLE</span></span>|<span data-ttu-id="39847-263">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-263">String</span></span>|  
|<span data-ttu-id="39847-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39847-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="39847-265">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-265">String</span></span>|  
|<span data-ttu-id="39847-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39847-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="39847-267">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-267">String</span></span>|  
|<span data-ttu-id="39847-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="39847-269">Byte</span><span class="sxs-lookup"><span data-stu-id="39847-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="39847-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="39847-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="39847-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-271">ColumnName</span></span>|<span data-ttu-id="39847-272">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="39847-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="39847-274">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-274">String</span></span>|  
|<span data-ttu-id="39847-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="39847-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="39847-276">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-276">String</span></span>|  
|<span data-ttu-id="39847-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="39847-278">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-278">String</span></span>|  
|<span data-ttu-id="39847-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-279">COLUMN_NAME</span></span>|<span data-ttu-id="39847-280">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-280">String</span></span>|  
|<span data-ttu-id="39847-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-281">COLUMN_TYPE</span></span>|<span data-ttu-id="39847-282">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-282">Int16</span></span>|  
|<span data-ttu-id="39847-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-283">DATA_TYPE</span></span>|<span data-ttu-id="39847-284">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-284">Int16</span></span>|  
|<span data-ttu-id="39847-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-285">TYPE_NAME</span></span>|<span data-ttu-id="39847-286">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-286">String</span></span>|  
|<span data-ttu-id="39847-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="39847-287">COLUMN_SIZE</span></span>|<span data-ttu-id="39847-288">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-288">Int32</span></span>|  
|<span data-ttu-id="39847-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="39847-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="39847-290">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-290">Int32</span></span>|  
|<span data-ttu-id="39847-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="39847-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="39847-292">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-292">Int16</span></span>|  
|<span data-ttu-id="39847-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="39847-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="39847-294">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-294">Int16</span></span>|  
|<span data-ttu-id="39847-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="39847-295">NULLABLE</span></span>|<span data-ttu-id="39847-296">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-296">Int16</span></span>|  
|<span data-ttu-id="39847-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-297">REMARKS</span></span>|<span data-ttu-id="39847-298">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-298">String</span></span>|  
|<span data-ttu-id="39847-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="39847-299">COLUMN_DEF</span></span>|<span data-ttu-id="39847-300">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-300">String</span></span>|  
|<span data-ttu-id="39847-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="39847-302">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-302">Int16</span></span>|  
|<span data-ttu-id="39847-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="39847-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="39847-304">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-304">Int16</span></span>|  
|<span data-ttu-id="39847-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="39847-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="39847-306">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-306">Int32</span></span>|  
|<span data-ttu-id="39847-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="39847-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="39847-308">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-308">Int32</span></span>|  
|<span data-ttu-id="39847-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="39847-309">IS_NULLABLE</span></span>|<span data-ttu-id="39847-310">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-310">String</span></span>|  
|<span data-ttu-id="39847-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="39847-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="39847-312">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-312">String</span></span>|  
|<span data-ttu-id="39847-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="39847-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="39847-314">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-314">String</span></span>|  
|<span data-ttu-id="39847-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="39847-316">Byte</span><span class="sxs-lookup"><span data-stu-id="39847-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="39847-317">Драйвер ODBC для Oracle (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="39847-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="39847-318">Microsoft SQL Server драйвер ODBC для Oracle поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем.</span><span class="sxs-lookup"><span data-stu-id="39847-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="39847-319">Таблицы</span><span class="sxs-lookup"><span data-stu-id="39847-319">Tables</span></span>  
  
-   <span data-ttu-id="39847-320">Столбцы</span><span class="sxs-lookup"><span data-stu-id="39847-320">Columns</span></span>  
  
-   <span data-ttu-id="39847-321">Процедуры</span><span class="sxs-lookup"><span data-stu-id="39847-321">Procedures</span></span>  
  
-   <span data-ttu-id="39847-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="39847-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="39847-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="39847-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="39847-324">Представления</span><span class="sxs-lookup"><span data-stu-id="39847-324">Views</span></span>  
  
-   <span data-ttu-id="39847-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="39847-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="39847-326">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="39847-326">Tables and Views</span></span>  
  
|<span data-ttu-id="39847-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-327">ColumnName</span></span>|<span data-ttu-id="39847-328">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="39847-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="39847-330">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-330">String</span></span>|  
|<span data-ttu-id="39847-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="39847-331">TABLE_OWNER</span></span>|<span data-ttu-id="39847-332">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-332">String</span></span>|  
|<span data-ttu-id="39847-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-333">TABLE_NAME</span></span>|<span data-ttu-id="39847-334">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-334">String</span></span>|  
|<span data-ttu-id="39847-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-335">TABLE_TYPE</span></span>|<span data-ttu-id="39847-336">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-336">String</span></span>|  
|<span data-ttu-id="39847-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-337">REMARKS</span></span>|<span data-ttu-id="39847-338">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="39847-339">Столбцы</span><span class="sxs-lookup"><span data-stu-id="39847-339">Columns</span></span>  
  
|<span data-ttu-id="39847-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-340">ColumnName</span></span>|<span data-ttu-id="39847-341">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="39847-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="39847-343">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-343">String</span></span>|  
|<span data-ttu-id="39847-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="39847-344">TABLE_OWNER</span></span>|<span data-ttu-id="39847-345">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-345">String</span></span>|  
|<span data-ttu-id="39847-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-346">TABLE_NAME</span></span>|<span data-ttu-id="39847-347">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-347">String</span></span>|  
|<span data-ttu-id="39847-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-348">COLUMN_NAME</span></span>|<span data-ttu-id="39847-349">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-349">String</span></span>|  
|<span data-ttu-id="39847-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-350">DATA_TYPE</span></span>|<span data-ttu-id="39847-351">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-351">Int16</span></span>|  
|<span data-ttu-id="39847-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-352">TYPE_NAME</span></span>|<span data-ttu-id="39847-353">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-353">String</span></span>|  
|<span data-ttu-id="39847-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="39847-354">PRECISION</span></span>|<span data-ttu-id="39847-355">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-355">Int32</span></span>|  
|<span data-ttu-id="39847-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="39847-356">LENGTH</span></span>|<span data-ttu-id="39847-357">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-357">Int32</span></span>|  
|<span data-ttu-id="39847-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="39847-358">SCALE</span></span>|<span data-ttu-id="39847-359">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-359">Int16</span></span>|  
|<span data-ttu-id="39847-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="39847-360">RADIX</span></span>|<span data-ttu-id="39847-361">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-361">Int16</span></span>|  
|<span data-ttu-id="39847-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="39847-362">NULLABLE</span></span>|<span data-ttu-id="39847-363">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-363">Int16</span></span>|  
|<span data-ttu-id="39847-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-364">REMARKS</span></span>|<span data-ttu-id="39847-365">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-365">String</span></span>|  
|<span data-ttu-id="39847-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="39847-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="39847-367">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="39847-368">Процедуры</span><span class="sxs-lookup"><span data-stu-id="39847-368">Procedures</span></span>  
  
|<span data-ttu-id="39847-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-369">ColumnName</span></span>|<span data-ttu-id="39847-370">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="39847-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="39847-372">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-372">String</span></span>|  
|<span data-ttu-id="39847-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="39847-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="39847-374">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-374">String</span></span>|  
|<span data-ttu-id="39847-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="39847-376">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-376">String</span></span>|  
|<span data-ttu-id="39847-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="39847-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="39847-378">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-378">Int16</span></span>|  
|<span data-ttu-id="39847-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="39847-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="39847-380">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-380">Int16</span></span>|  
|<span data-ttu-id="39847-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="39847-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="39847-382">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-382">Int16</span></span>|  
|<span data-ttu-id="39847-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-383">REMARKS</span></span>|<span data-ttu-id="39847-384">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-384">String</span></span>|  
|<span data-ttu-id="39847-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="39847-386">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="39847-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="39847-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="39847-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-388">ColumnName</span></span>|<span data-ttu-id="39847-389">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="39847-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="39847-391">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-391">String</span></span>|  
|<span data-ttu-id="39847-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="39847-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="39847-393">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-393">String</span></span>|  
|<span data-ttu-id="39847-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="39847-395">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-395">String</span></span>|  
|<span data-ttu-id="39847-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-396">COLUMN_NAME</span></span>|<span data-ttu-id="39847-397">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-397">String</span></span>|  
|<span data-ttu-id="39847-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-398">COLUMN_TYPE</span></span>|<span data-ttu-id="39847-399">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-399">Int16</span></span>|  
|<span data-ttu-id="39847-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-400">DATA_TYPE</span></span>|<span data-ttu-id="39847-401">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-401">Int16</span></span>|  
|<span data-ttu-id="39847-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-402">TYPE_NAME</span></span>|<span data-ttu-id="39847-403">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-403">String</span></span>|  
|<span data-ttu-id="39847-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="39847-404">PRECISION</span></span>|<span data-ttu-id="39847-405">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-405">Int32</span></span>|  
|<span data-ttu-id="39847-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="39847-406">LENGTH</span></span>|<span data-ttu-id="39847-407">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-407">Int32</span></span>|  
|<span data-ttu-id="39847-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="39847-408">SCALE</span></span>|<span data-ttu-id="39847-409">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-409">Int16</span></span>|  
|<span data-ttu-id="39847-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="39847-410">RADIX</span></span>|<span data-ttu-id="39847-411">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-411">Int16</span></span>|  
|<span data-ttu-id="39847-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="39847-412">NULLABLE</span></span>|<span data-ttu-id="39847-413">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-413">Int16</span></span>|  
|<span data-ttu-id="39847-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-414">REMARKS</span></span>|<span data-ttu-id="39847-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-415">String</span></span>|  
|<span data-ttu-id="39847-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="39847-416">OVERLOAD</span></span>|<span data-ttu-id="39847-417">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-417">Int32</span></span>|  
|<span data-ttu-id="39847-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="39847-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="39847-419">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="39847-420">Драйвер ODBC для Jet (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="39847-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="39847-421">Драйвер ODBC для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="39847-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="39847-422">Таблицы</span><span class="sxs-lookup"><span data-stu-id="39847-422">Tables</span></span>  
  
-   <span data-ttu-id="39847-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="39847-423">Indexes</span></span>  
  
-   <span data-ttu-id="39847-424">Столбцы</span><span class="sxs-lookup"><span data-stu-id="39847-424">Columns</span></span>  
  
-   <span data-ttu-id="39847-425">Процедуры</span><span class="sxs-lookup"><span data-stu-id="39847-425">Procedures</span></span>  
  
-   <span data-ttu-id="39847-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="39847-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="39847-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="39847-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="39847-428">Представления</span><span class="sxs-lookup"><span data-stu-id="39847-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="39847-429">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="39847-429">Tables and Views</span></span>  
  
|<span data-ttu-id="39847-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-430">ColumnName</span></span>|<span data-ttu-id="39847-431">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="39847-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="39847-433">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-433">String</span></span>|  
|<span data-ttu-id="39847-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="39847-434">TABLE_OWNER</span></span>|<span data-ttu-id="39847-435">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-435">String</span></span>|  
|<span data-ttu-id="39847-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-436">TABLE_NAME</span></span>|<span data-ttu-id="39847-437">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-437">String</span></span>|  
|<span data-ttu-id="39847-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-438">TABLE_TYPE</span></span>|<span data-ttu-id="39847-439">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-439">String</span></span>|  
|<span data-ttu-id="39847-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-440">REMARKS</span></span>|<span data-ttu-id="39847-441">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="39847-442">Столбцы</span><span class="sxs-lookup"><span data-stu-id="39847-442">Columns</span></span>  
  
|<span data-ttu-id="39847-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-443">ColumnName</span></span>|<span data-ttu-id="39847-444">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="39847-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="39847-446">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-446">String</span></span>|  
|<span data-ttu-id="39847-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="39847-447">TABLE_OWNER</span></span>|<span data-ttu-id="39847-448">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-448">String</span></span>|  
|<span data-ttu-id="39847-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-449">TABLE_NAME</span></span>|<span data-ttu-id="39847-450">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-450">String</span></span>|  
|<span data-ttu-id="39847-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-451">COLUMN_NAME</span></span>|<span data-ttu-id="39847-452">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-452">String</span></span>|  
|<span data-ttu-id="39847-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-453">DATA_TYPE</span></span>|<span data-ttu-id="39847-454">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-454">Int16</span></span>|  
|<span data-ttu-id="39847-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-455">TYPE_NAME</span></span>|<span data-ttu-id="39847-456">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-456">String</span></span>|  
|<span data-ttu-id="39847-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="39847-457">PRECISION</span></span>|<span data-ttu-id="39847-458">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-458">Int32</span></span>|  
|<span data-ttu-id="39847-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="39847-459">LENGTH</span></span>|<span data-ttu-id="39847-460">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-460">Int32</span></span>|  
|<span data-ttu-id="39847-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="39847-461">SCALE</span></span>|<span data-ttu-id="39847-462">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-462">Int16</span></span>|  
|<span data-ttu-id="39847-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="39847-463">RADIX</span></span>|<span data-ttu-id="39847-464">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-464">Int16</span></span>|  
|<span data-ttu-id="39847-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="39847-465">NULLABLE</span></span>|<span data-ttu-id="39847-466">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-466">Int16</span></span>|  
|<span data-ttu-id="39847-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-467">REMARKS</span></span>|<span data-ttu-id="39847-468">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-468">String</span></span>|  
|<span data-ttu-id="39847-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="39847-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="39847-470">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="39847-471">Процедуры</span><span class="sxs-lookup"><span data-stu-id="39847-471">Procedures</span></span>  
  
|<span data-ttu-id="39847-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-472">ColumnName</span></span>|<span data-ttu-id="39847-473">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="39847-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="39847-475">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-475">String</span></span>|  
|<span data-ttu-id="39847-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="39847-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="39847-477">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-477">String</span></span>|  
|<span data-ttu-id="39847-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="39847-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-479">String</span></span>|  
|<span data-ttu-id="39847-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="39847-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="39847-481">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-481">Int16</span></span>|  
|<span data-ttu-id="39847-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="39847-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="39847-483">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-483">Int16</span></span>|  
|<span data-ttu-id="39847-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="39847-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="39847-485">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-485">Int16</span></span>|  
|<span data-ttu-id="39847-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-486">REMARKS</span></span>|<span data-ttu-id="39847-487">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-487">String</span></span>|  
|<span data-ttu-id="39847-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="39847-489">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="39847-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="39847-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="39847-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-491">ColumnName</span></span>|<span data-ttu-id="39847-492">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="39847-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="39847-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-494">String</span></span>|  
|<span data-ttu-id="39847-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="39847-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="39847-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-496">String</span></span>|  
|<span data-ttu-id="39847-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="39847-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-498">String</span></span>|  
|<span data-ttu-id="39847-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-499">COLUMN_NAME</span></span>|<span data-ttu-id="39847-500">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-500">String</span></span>|  
|<span data-ttu-id="39847-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-501">COLUMN_TYPE</span></span>|<span data-ttu-id="39847-502">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-502">Int16</span></span>|  
|<span data-ttu-id="39847-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-503">DATA_TYPE</span></span>|<span data-ttu-id="39847-504">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-504">Int16</span></span>|  
|<span data-ttu-id="39847-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-505">TYPE_NAME</span></span>|<span data-ttu-id="39847-506">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-506">String</span></span>|  
|<span data-ttu-id="39847-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="39847-507">PRECISION</span></span>|<span data-ttu-id="39847-508">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-508">Int32</span></span>|  
|<span data-ttu-id="39847-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="39847-509">LENGTH</span></span>|<span data-ttu-id="39847-510">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-510">Int32</span></span>|  
|<span data-ttu-id="39847-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="39847-511">SCALE</span></span>|<span data-ttu-id="39847-512">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-512">Int16</span></span>|  
|<span data-ttu-id="39847-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="39847-513">RADIX</span></span>|<span data-ttu-id="39847-514">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-514">Int16</span></span>|  
|<span data-ttu-id="39847-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="39847-515">NULLABLE</span></span>|<span data-ttu-id="39847-516">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-516">Int16</span></span>|  
|<span data-ttu-id="39847-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-517">REMARKS</span></span>|<span data-ttu-id="39847-518">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-518">String</span></span>|  
|<span data-ttu-id="39847-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="39847-519">OVERLOAD</span></span>|<span data-ttu-id="39847-520">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-520">Int32</span></span>|  
|<span data-ttu-id="39847-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="39847-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="39847-522">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="39847-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="39847-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="39847-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="39847-524">ColumnName</span></span>|<span data-ttu-id="39847-525">DataType</span><span class="sxs-lookup"><span data-stu-id="39847-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="39847-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="39847-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="39847-527">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-527">String</span></span>|  
|<span data-ttu-id="39847-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="39847-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="39847-529">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-529">String</span></span>|  
|<span data-ttu-id="39847-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="39847-531">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-531">String</span></span>|  
|<span data-ttu-id="39847-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-532">COLUMN_NAME</span></span>|<span data-ttu-id="39847-533">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-533">String</span></span>|  
|<span data-ttu-id="39847-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-534">COLUMN_TYPE</span></span>|<span data-ttu-id="39847-535">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-535">Int16</span></span>|  
|<span data-ttu-id="39847-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-536">DATA_TYPE</span></span>|<span data-ttu-id="39847-537">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-537">Int16</span></span>|  
|<span data-ttu-id="39847-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="39847-538">TYPE_NAME</span></span>|<span data-ttu-id="39847-539">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-539">String</span></span>|  
|<span data-ttu-id="39847-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="39847-540">COLUMN_SIZE</span></span>|<span data-ttu-id="39847-541">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-541">Int32</span></span>|  
|<span data-ttu-id="39847-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="39847-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="39847-543">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-543">Int32</span></span>|  
|<span data-ttu-id="39847-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="39847-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="39847-545">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-545">Int16</span></span>|  
|<span data-ttu-id="39847-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="39847-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="39847-547">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-547">Int16</span></span>|  
|<span data-ttu-id="39847-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="39847-548">NULLABLE</span></span>|<span data-ttu-id="39847-549">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-549">Int16</span></span>|  
|<span data-ttu-id="39847-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="39847-550">REMARKS</span></span>|<span data-ttu-id="39847-551">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-551">String</span></span>|  
|<span data-ttu-id="39847-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="39847-552">COLUMN_DEF</span></span>|<span data-ttu-id="39847-553">Строковое</span><span class="sxs-lookup"><span data-stu-id="39847-553">String</span></span>|  
|<span data-ttu-id="39847-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="39847-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="39847-555">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-555">Int16</span></span>|  
|<span data-ttu-id="39847-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="39847-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="39847-557">Int16</span><span class="sxs-lookup"><span data-stu-id="39847-557">Int16</span></span>|  
|<span data-ttu-id="39847-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="39847-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="39847-559">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-559">Int32</span></span>|  
|<span data-ttu-id="39847-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="39847-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="39847-561">Int32</span><span class="sxs-lookup"><span data-stu-id="39847-561">Int32</span></span>|  
|<span data-ttu-id="39847-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="39847-562">IS_NULLABLE</span></span>|<span data-ttu-id="39847-563">String</span><span class="sxs-lookup"><span data-stu-id="39847-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39847-564">См. также</span><span class="sxs-lookup"><span data-stu-id="39847-564">See Also</span></span>  
 [<span data-ttu-id="39847-565">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="39847-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

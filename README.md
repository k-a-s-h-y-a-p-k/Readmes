# NeutriSense-AI

A comprehensive AI system analyzing Indian food recipes through database lookup, recipe modification, nutritional comparison, and image classification to provide comprehensive dietary insights.Designed to provide accurate nutritional guidance for Indian cuisine with fallback estimation capabilities.

## Overview

NutriSense AI is an end-to-end AI system for analyzing Indian food nutrition using
database lookup, image classification, and intelligent recipe modifications.
It addresses the lack of accurate Indian food representation in commercial nutrition APIs.

The system unifies multiple data sources and AI techniques to provide:
- Database-driven lookups for 725+ curated recipes with complete nutritional profiles
- Intelligent image classification across 148 Indian dish categories
- AI-powered recipe modifications (e.g., "low-calorie version of Paneer Butter Masala")
- Multi-recipe comparison with optional nutritional summaries
- Fallback LLM estimation for out-of-database queries

## Why This Matters:

- Domain Gap: Indian cuisines are underrepresented in commercial nutrition APIs
- Data Fusion: Unified heterogeneous datasets using custom fuzzy matching (Nutritional values + Cooking methods/Ingredients)
- Multi-Modal Access: Users can query via text or images


## Features

### 1. Database Lookup (Pathway 1)

- Direct extraction of recipes and nutritional information from the unified dataset
- Cleaning and fuzzy matching for accurate recipe identification
- Custom composite scoring for ranking results
- Returns complete nutritional breakdown for queried dishes

### 2.Recipe Modification (Pathway 2)

- Router passes the extracted dish and constraint from the query
- The obtained dish is extracted from the database
- the data from the database and the user constraint is passed to LLM engine
- The LLM engine generates modified instructions while maintaining nutritional accuracy
- Preserves dish authenticity while meeting dietary requirements

### 3.Nutritional Comparison (Pathway 3)

- Compare nutritional profiles of two recipes side-by-side
- Displays macro/micronutrient breakdown for both
- LLM-generated summary highlighting the healthier option
- Helps users make informed dietary choices

### 4.Image Classification (Pathway 4)

- Upload food images for automatic dish recognition
- **EfficientNet-B4** trained on **148 classes Indian food image dataset**
- Classified dishes automatically routed through Pathway 1
- Top-3 accuracy: 85.20%

### 5.Router 

- The Router classifies the user query as intent using LLM
- Handles the execution of all the pathways(1,2 & 3)
- Extracts the dish mentioned by the user using LLM

### 6. LLM Fallback Estimator

- Intelligent fallback when dishes aren't found in the database
- Obtains most similar dish from the database (uses Pathway 1)
- Uses LLM to estimate the range of plausible nutrition for the dish
- Clearly marked with lower confidence with warnings

  

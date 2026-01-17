# NeutriSense-AI

A comprehensive AI system analyzing Indian food recipes through database lookup, recipe modification, nutritional comparison, and image classification to provide comprehensive dietary insights.Designed to provide accurate nutritional guidance for Indian cuisine with fallback estimation capabilities.
---
## Overview

NutriSense AI is a comprehensive nutrition analysis platform designed specifically for Indian food. The system intelligently routes user queries through four distinct pathways to provide accurate nutritional information, recipe modifications, comparative analysis, and image-based food recognition.
NutriSense AI addresses the challenge of accurate nutritional tracking for Indian food, which is underrepresented in mainstream nutrition applications. The system unifies multiple data sources and AI techniques to provide:
- Database-driven lookups for 725+ curated recipes with complete nutritional profiles
- Intelligent image classification across 148 Indian dish categories
- AI-powered recipe modifications (e.g., "low-calorie version of Paneer Butter Masala")
- Multi-recipe comparison with optional nutritional summaries
- Fallback LLM estimation for out-of-database queries

Why This Matters:

- Domain Gap: Indian cuisines are underrepresented in commercial nutrition APIs
- Data Fusion: Unified heterogeneous datasets using custom fuzzy matching (Nutritional values + Cooking methods/Ingredients)
- Multi-Modal Access: Users can query via text or images
---

## Features

### 1. Database Lookup (Pathway 1)

- Direct extraction of recipes and nutritional information from the unified dataset
- Cleaning and fuzzy matching for accurate recipe identification
- Custom composite scoring for ranking results
- Returns complete nutritional breakdown for queried dishes

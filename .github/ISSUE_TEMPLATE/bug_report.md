---
name: Bug report
about: Create a report to help us improve
title: ''
labels: ''
assignees: ''

---

import 'package:flutter/material.dart';
import 'package:meals_app/dummy_data.dart';
import 'package:collection/collection.dart';

class MealDetailScreen extends StatelessWidget {
  static const routeName = '/meal_detail_screen';

  @override
  Widget build(BuildContext context) {
    final mealId = ModalRoute.of(context)!.settings.arguments.toString();
    final selectedMeal = DUMMY_MEALS.firstWhereOrNull(
      (meal) => meal.imageUrl == 'mealId',
    );
    return Scaffold(
      appBar: AppBar(
        title: Text('$mealId'),
      ),
      body: Column(
        children: [
          Container(
            height: 300,
            width: double.infinity,
            child: Image.network(
              selectedMeal!.imageUrl,
              fit: BoxFit.cover,
            ),
          ),
        ],
      ),
    );
  }
}

# Patch Exercise Notes

## Summary

Fixed two high-value backend issues in the task search API.

1. Corrected SQL AND/OR precedence in `TaskRepository.java` so archived tasks are excluded and the optional status filter is applied correctly.
2. Removed the artificial `Thread.sleep` delay from `TaskController.java` so search requests are not intentionally slowed down based on query length.

## What I Did Not Change

I did not rewrite the existing application structure or introduce new libraries. The existing Spring Boot, repository, controller, frontend, and database setup were kept unchanged because the requested fixes could be made with small focused changes.

## Biggest Remaining Risk

The search and status filtering logic still relies on the existing controller-side pagination and status parsing. Additional validation for invalid status values and unusual pagination inputs could be useful in a future improvement.

## Tools / AI Used

Used VS Code, Git, GitHub, Maven, and API testing during the exercise. AI assistance was used to understand the existing code, identify likely root causes, explain the fixes, and provide guidance while keeping the changes focused on the identified bugs.
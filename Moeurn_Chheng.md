# DevOps Conception Class

- Student: [Moeurn Chheng]

## Lesson 2: My CI/CD pipeline

- Project: MeetSpace Management System
- Trigger: push to feature/room/search-listing
- Feature: “Search Available Room” from a Laravel API
- Target: Laravel staging server + Android testing device

### Pipeline design

Code -> Test -> Build -> Release -> Deploy

1. Code: commit API (api/room/listing/search) and Screen (RoomListSearch.dart) |  
   developer | commit | manual
2. Test: check API (api/room/listing/search) and Screen (Search List) | developer | test
   result | auto
3. Build: package API + APK | artifact | commit | auto
4. Release: approve v1.0.0 | release lead | approved version | manual
5. Deploy: stage API; Install APK | ops/tester | running app | manual

### Controls

On test/build failure: Stop fix and retest | Release approval by: Project Manager / Lead Developer
After deployment, check: API endpoint & Room search UI | If it fails: Roll back to prevoius stable release
Feedback for the next change: Monitor and collect feedback and Plan the next code
Optional drawing: ![My pipeline](moeurn_chheng.png)

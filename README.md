# Node-RED CV Template Dashboard

A professional, dynamic CV/Resume template built with FlowFuse Node-RED Dashboard 2.0.

## Features

✨ **Dynamic Template** - No hard-coded data, accepts JSON input
📱 **Responsive Design** - Works on desktop and mobile devices
🎨 **Professional Layout** - Clean, modern design with sections for:
- Profile photo and contact information
- Skills with gradient badges
- Work experience with detailed tasks
- Education history
- Professional links (GitHub, ORCID, IEEE)

## Installation

### 1. Install FlowFuse Dashboard 2.0
```bash
npm install @flowfuse/node-red-dashboard
```

### 2. Import the Flow
1. Open Node-RED
2. Click the menu (≡) in the top-right corner
3. Select **Import**
4. Choose `cv-template-flow.json`
5. Click **Import**
6. Deploy the flow

### 3. Access the Dashboard
Navigate to: `http://your-node-red-url/dashboard/cv`

## Usage

### Loading CV Data

The flow automatically loads sample data on startup. You can update the CV data in three ways:

#### Method 1: Modify the Inject Node
1. Double-click the "Load CV Data" inject node
2. Update the JSON payload with your CV data
3. Deploy and inject

#### Method 2: Use External Data Source
Replace the inject node with:
- HTTP Request node (fetch from API)
- File Read node (load from file)
- MQTT/Database nodes (dynamic sources)

#### Method 3: Manual Update
1. Click the "Reload CV" button on the dashboard
2. This refreshes the display with the current data

## Data Structure

```json
{
  "userId": "unique-user-id",
  "title": "Your Professional Title",
  "email": "your.email@example.com",
  "phone": "+00-000-000-0000",
  "address": "Your Full Address",
  "skills": ["Skill 1", "Skill 2", "Skill 3"],
  "jobs": [
    {
      "company": "Company Name",
      "position": "Job Title",
      "startDate": "Month Year",
      "endDate": "Month Year or Present",
      "tasks": [
        "Task/Achievement 1",
        "Task/Achievement 2"
      ]
    }
  ],
  "schools": [
    {
      "degree": "Degree Name",
      "schoolName": "Institution Name",
      "startDate": "Month Year",
      "endDate": "Month Year"
    }
  ],
  "links": {
    "github": "https://github.com/username",
    "orcid": "https://orcid.org/0000-0000-0000-0000",
    "ieee": "https://ieeexplore.ieee.org/author/..."
  },
  "imageSrc": "https://url-to-your-photo.png"
}
```

## Customization

### Change Colors
Edit the `cv_theme` node to customize colors:
- `surface`: Background color
- `primary`: Primary accent color
- `bgPage`: Page background
- `groupBg`: Group background
- `groupOutline`: Border colors

### Modify Layout
Edit the `<style>` section in the `cv_template` node to adjust:
- Fonts and sizes
- Spacing and margins
- Colors and gradients
- Responsive breakpoints

### Add New Sections
1. Update the data structure
2. Add new sections in the `<template>` part of the `cv_template` node
3. Style the new sections in the `<style>` section

## Integration Examples

### Load from HTTP API
```javascript
// Replace inject node with HTTP request
GET https://your-api.com/cv/user123
```

### Load from Database
```javascript
// Add database query node
SELECT * FROM cv_data WHERE user_id = '...'
```

### Dynamic User Selection
Add a dropdown to select different CVs:
1. Add ui-dropdown node
2. Connect to function node that fetches user-specific data
3. Flow to cv_template node

## Sample Data

See `cv-sample-data.json` for a complete example with all fields populated.

## Requirements

- Node-RED v3.0 or higher
- @flowfuse/node-red-dashboard v1.0 or higher

## License

Free to use and modify for personal and commercial projects.

## Support

For issues or questions about:
- Node-RED: https://nodered.org
- FlowFuse Dashboard: https://dashboard.flowfuse.com

---

**Made with ❤️ using Node-RED and FlowFuse Dashboard 2.0**

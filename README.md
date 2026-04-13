🚨 Incident Response Buckets
An interactive incident management tool for Lisinski Law Firm that organizes critical response scenarios into categorized buckets. Built as a standalone web app powered by Supabase for real-time persistent storage.

✨ Features

6 default incident buckets covering Security, Technology, Political, Legal, Reputation, and Facilities
Add & edit incidents — any team member can contribute new items
Admin controls — only authorized admins can delete items or buckets
Add custom buckets — expandable beyond the 6 defaults
Drag-and-drop reordering — reorganize buckets in any order
Collapse/expand buckets — reduce clutter when reviewing
Color themes — 8 color options per bucket
Global search — find any incident across all buckets instantly
Filter by owner — view buckets by responsible team
Jump navigation — one-click scroll to any bucket
Last updated timestamp — see when each bucket was last modified
CSV export — download the full list as a spreadsheet
Real-time sync — all changes persist instantly via Supabase


🪣 Default Buckets
#BucketLikely Owner1Security & Physical SafetySecurity + HR2Technology & OperationsIT + Operations3Political & Social UnrestHR + Legal + Marketing/Comms4Legal IssuesLegal + Marketing5Reputation & BrandMarketing + Legal + HR6Facilities & Vendor DisruptionsProcurement + Operations

🚀 Deployment
This project is hosted via GitHub Pages and requires no build step. It is a single self-contained index.html file.
Live URL:
https://yourusername.github.io/incident-response-buckets/
To update the app, edit index.html and commit the changes to the main branch. GitHub Pages will redeploy automatically within 1–2 minutes.

🗄️ Database
Data is stored in Supabase using the following table schema:
sqlcreate table incident_buckets (
  id            bigint generated always as identity primary key,
  bucket_order  integer      not null default 1,
  name          text         not null,
  description   text         default '',
  owner         text         default '',
  theme         text         default 'red',
  items         jsonb        default '[]',
  updated_at    timestamptz  default now()
);
All reads and writes go directly from the browser to Supabase via its REST API. No backend server required.

🔐 Admin Access
The app has two access levels:
RoleCan Add ItemsCan Edit ItemsCan Delete ItemsCan Delete BucketsCan Add BucketsUser✅✅❌❌✅Admin✅✅✅✅✅
Admin credentials are stored in the app configuration. Contact the project owner to obtain access.

🛠️ Local Development
No build tools required. Simply open index.html in any modern browser:
bashgit clone https://github.com/yourusername/incident-response-buckets.git
cd incident-response-buckets
open index.html

Note: Direct file access (file://) may have CORS restrictions in some browsers. Use a simple local server if needed:
bashnpx serve .


📁 Project Structure
incident-response-buckets/
└── index.html      # Full application (React + Supabase, single file)
└── README.md       # This file

🤝 Contributing

Open an issue describing what you want to change
Or contact the project owner to request edits directly
Changes to index.html on the main branch deploy automatically

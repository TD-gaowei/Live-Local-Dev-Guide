# Live 项目本地运行指南

## 需要改动下面几个文件

enviorment.env

```text
// export const isDevelopmentEnv = process.env.NODE_ENV === "development";
export const isDevelopmentEnv = false;
// export const isAtlasMode = window.location.href.indexOf("/atlas") > -1;
export const isAtlasMode = true;

```

.env.development

```text
# REACT_APP_AUTO_UPDATE_POLLING_INTERVAL=
# REACT_APP_AUTO_UPDATE_BUNDLE_BASE_PATH=
# REACT_APP_DASHBOARDS_API_BASE_URL=/dashboards
# REACT_APP_SHARE_DASHBOARDS_API_BASE_URL=/dashboards/dashboard_id/share
# REACT_APP_METRICS_API_BASE_URL=/metrics
# REACT_APP_USER_BASE_URL=/user.json
# REACT_APP_LIST_USER_STATUSES_URL=/user-statuses.json
# REACT_APP_UPDATE_USER_STATUS_URL=/update-user-status.json
# REACT_APP_TEAMS_API_BASE_URL=/teams.json
# REACT_APP_RING_GROUPS_API_BASE_URL=/ring-groups.json
# REACT_APP_CCAAS_QUEUES_API_BASE_URL=/ccaas-queues.json
# REACT_APP_POLICIES_EVALUATE_BASE_URL=/policies.json
# REACT_APP_GRAPH_USERS=users.json
# REACT_APP_CAMPAIGNS_API_BASE_URL=/campaigns.json
# REACT_APP_RECORD_LISTS_API_BASE_URL=/record-lists.json
# ATLAS_MONITORING_URL=https://stg-cdn-talkdesk.talkdeskdev.com/atlas/latest/monitoring/monitoring.js
# REACT_APP_METRICS_REFRESH_RATE=15000

REACT_APP_BUNDLE_BASE_PATH=https://stg-cdn-talkdesk.talkdeskdev.com/reporting-live-dashboards-ui
REACT_APP_VERSION=$npm_package_version
REACT_APP_DASHBOARDS_API_BASE_URL=/users/user_id/reporting-dashboards
REACT_APP_SHARE_DASHBOARDS_API_BASE_URL=reporting-dashboards/dashboard_id/share
REACT_APP_METRICS_API_BASE_URL=/reporting-metrics
REACT_APP_TEAMS_API_BASE_URL=/teams
REACT_APP_RING_GROUPS_API_BASE_URL=/ring-groups
REACT_APP_USER_BASE_URL=/users
REACT_APP_LIST_USER_STATUSES_URL=/reporting-user-statuses
REACT_APP_UPDATE_USER_STATUS_URL=/salesforce/account/users
REACT_APP_POLICIES_EVALUATE_BASE_URL=/policies/evaluate/bulk
REACT_APP_GRAPH_USERS=/graph/users
REACT_APP_CCAAS_USERS_STATUS=/ccaas/users/status
REACT_APP_ACCOUNT_CUSTOM_STATUS=/account/custom-status
REACT_APP_OCCUPANCY_USERS_OCCUPANCY_STATUS=/occupancy/users/occupancy-status
REACT_APP_MULTICHANNEL_INTERACTION_ACTIONS=/omnichannel/inbox/interactions/interaction_id/actions
REACT_APP_MULTICHANNEL_INBOX_INTERACTIONS_BULK=/omnichannel/inbox/interactions/bulk
REACT_APP_MAX_SUBSCRIPTION_RETRY_ATTEMPTS=6
REACT_APP_SUBSCRIPTION_RETRY_BACKOFF_MS=5000
REACT_APP_AUTO_UPDATE_POLLING_INTERVAL=600000
REACT_APP_FAILED_LOADING_SUBSCRIPTION_RETRY_INTERVAL=1000
REACT_APP_FAILED_LOADING_SUBSCRIPTION_RETRY_ATTEMPTS=3
REACT_APP_AUTO_UPDATE_BUNDLE_BASE_PATH=https://prd-cdn-talkdesk.talkdesk.com/reporting-live-dashboards-ui
ESLINT_NO_DEV_ERRORS=true
REACT_APP_CAMPAIGNS_API_BASE_URL=/campaigns
REACT_APP_RECORD_LISTS_API_BASE_URL=/record-lists
ATLAS_MONITORING_URL=
REACT_APP_METRICS_REFRESH_RATE=15000
```

src/index.ts

```text
// if (isAtlasMode) {
//   atlasEntrypoint.start();
// } else if (isDevelopmentEnv) {
//   devEntrypoint.start();
// }

atlasEntrypoint.start();
```

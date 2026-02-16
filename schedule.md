---
layout: page
title: 3. Course Schedule
description: Weekly course schedule, including readings, quizzes, and assignments.
---

# Schedule



<div id="schedule-su-tue-thu">
  {% include module-su-tue-thu.html %}
</div>



{% raw %}
<script>
(function() {
  function init() {
    var su = document.getElementById("schedule-su-tue-thu");
    if (su) {
      su.style.display = "block"; // Ensure it's visible
    }
  }
  
  if (document.readyState === 'loading') {
    document.addEventListener('DOMContentLoaded', init);
  } else {
    init();
  }
})();
</script>
{% endraw %}




<!-- ---
layout: page
title: 3. Course Schedule
description: Weekly course schedule, including readings, quizzes, and assignments.
---

# Schedule

{% for module in site.modules %}
{{ module }}
{% endfor %} -->
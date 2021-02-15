<template>
  <div>
      <div class="repo__row">
        <div class="left__content">
          <div class="top__row">
            <a href="#" class="name">{{ name }}</a>
          </div>
          <div class="desc">{{ description }}</div>
          <div class="bottom__row">
            <span v-if="language == 'JavaScript'">
              <span
                class="language"
                :style="{ backgroundColor: '#f1e05a' }"
              ></span>
              <span class="item">{{ language }}</span>
            </span>
            <span v-else-if="language == 'HTML'">
              <span
                class="language"
                :style="{ backgroundColor: '#e34c26' }"
              ></span>
              <span class="item">{{ language }}</span>
            </span>
            <span v-else-if="language == 'CSS'">
              <span
                class="language"
                :style="{ backgroundColor: '#563d7c' }"
              ></span>
              <span class="item">{{ language }}</span>
            </span>
            <span v-else-if="language == 'Vue'">
              <span
                class="language"
                :style="{ backgroundColor: '#2c3e50' }"
              ></span>
              <span class="item">{{ language }}</span>
            </span>


            <span class="item" v-if="stargazers_count > 0">
													<span>{{stargazers_count}}</span>
														<img src="../assets/star.svg" alt=""> 
												</span>

                        	<span class="item">{{calculateRelativeDate(updated_at)}}
									</span>

          </div>
        </div>


							<div class="right__content">
								<button class="star">
									<img src="../assets/star.svg" alt=""> <span>Star</span>
								</button>
							</div>
      </div>
  </div>
</template>

<script>
export default {
  name: "Repo",
  props: [
    "name",
    "language",
    "updated_at",
    "stargazers_count",
    "fork",
    "forks_url",
    "description",
  ],
  methods: {

    calculateRelativeDate: function (date) {
      const repoDate = new Date(date);
	const today = new Date();

	const minute = 60 * 1000;
	const hour = 60 * minute;
	const day = 24 * hour;
	const month = 30 * day;

	const timeDifference = today.getTime() - repoDate.getTime();

	const seconds = Math.floor(repoDate.getTime() / 1000);
	const currentSeconds = Math.floor(today.getTime() / 1000);
	const dateMonth = repoDate.getMonth();
	const currentMonth = today.getMonth();
	const currentYear = today.getFullYear();
	const currentDay = today.getDate();
	const dateDay = repoDate.getDate();
	const dayDifference = currentDay - dateDay;

	const daysInCurrentMonth = new Date(currentYear, currentMonth, 0).getDate();
	const secondsDifference = currentSeconds - seconds;

	const isThisMonth = today.getMonth() === dateMonth;
	const isThisYear = today.getFullYear() === repoDate.getFullYear();

	const monthNames = [
		'Jan',
		'Feb',
		'Mar',
		'Apr',
		'May',
		'Jun',
		'Jul',
		'Aug',
		'Sept',
		'Oct',
		'Nov',
		'Dec',
	];

	//Return day and year updated if date not in current year
	if (isThisYear) {
		if (!isThisMonth) {
			return `Updated on ${repoDate.getDate()} ${monthNames[dateMonth]}`;
		}

		if (currentDay < daysInCurrentMonth && dayDifference > 0) {
			return `Updated ${dayDifference} ${dayDifference > 1 ? 'days' : 'day'} ago`;
		}

		switch (true) {
			case Math.floor(timeDifference / month) > 1:
				return `Updated ${Math.floor(timeDifference / month)} minutes ago`;

			case Math.floor(timeDifference / minute) > 1:
				if (Math.floor(timeDifference / minute) > 60) {
					return `Updated ${Math.floor(timeDifference / minute / 60)} hours ago`;
				}

				return `Updated ${Math.floor(timeDifference / minute)} minutes ago`;

			default:
				return `Updated ${secondsDifference} seconds ago`;
		}
	} else {
		return `Updated on ${repoDate.getDate()} ${
			monthNames[dateMonth]
		} ${repoDate.getFullYear()}`;
	}
    }
  },
  mounted(){
    this.calculateRelativeDate()
  }
};
</script>

<style>
</style>
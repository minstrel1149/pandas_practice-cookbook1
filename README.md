# Pandas Cookbook 연습 - 매트 해리슨 등 저

### 중요사항
1. 이전 여러 번 학습하였으나, 새로운 마음으로 다시 학습 및 코드 주석 추가
- 너무나도 당연한 것(e.g. 열 선택 등)은 그냥 패스
- 주석을 추가하느라 시간이 오래 걸리긴 하는데.. 더 자세히 공부하는 취지로 접근
- 주석을 통해 다른 곳에서도 내 Github 접속함을 통해 눈으로 복습 가능
2. 책에 있는 코드를 단순히 따라하는 것이 아니라 나만의 코드로 작성
3. 변수명의 경우 Snake Case 활용
4. 커널은 jupyter notebook의 파이썬 3.9.12 활용

## README.md 변경 진행 중

### Chapter 1. Pandas 기초
1. df.head(n), df.tail(n) 메서드
2. df.columns, df.index, df.values 속성, df.to_numpy() 메서드
3. df.dtypes 속성, df.astype(type) 메서드
4. df.info() 메서드
5. df.size, df.shape, df.ndim 속성, df.count() 메서드
6. ser.unique(), ser.nunique() 메서드
7. ser.sample(n, random_state) 메서드
8. ser.value_counts(normalize, sort, ascending, dropna) 메서드
9. df.describe(percentiles, include/exclude), df.quantile(q) 메서드
10. df.isna(), df.notna(), df.fillna(value, method), df.dropna(how) 메서드, ser.hasnans 속성
11. df.add(other, fill_value) 메서드 등
12. df.rename(mapper, axis, level) 메서드
13. df.assign(**kwargs), df.insert(loc, col_name, value) 메서드
14. df.all(), df.any() 메서드
15. Index.get_loc(key) 메서드

### Chapter 2. 기본 DataFrame 연산
1. df.select_dtypes(include/exclude) 메서드
2. df.filter(like/items/regex) 메서드
3. df.reindex(labels), df.reindex_like(other, method) 메서드
4. df.min(skipna, axis) 메서드 등
5. df.equals(df) 메서드, pd.testing.assert_frame_equal(left, right, check_dtype) 함수 등
6. df.cumsum(axis), df.cummax/cummmin(axis) 메서드
7. df.sort_values(by, ascending, kind, key), df.sort_index(level, axis, ascending, kind, key) 메서드

### Chapter 3. DataFrame 생성과 유지
1. pd.DataFrame(data, index, column) 함수
2. pd.read_csv(path or buffer, dtype, index_col, usecols, nrows, parse_dates, ...) 함수
3. df.memory_usage(deep) 메서드
4. pd.ExcelWriter(path, engine) 함수
5. pd.read_json(path or buffer, orient, ...) 함수

### Chapter 4. 데이터 분석 시작
1. df.nlargest/nsmallest(n, columns, keep) 메서드
2. df.drop_duplicates(subset, keep) 메서드
3. df.droplevel(level, axis) 메서드
4. df.apply(func, axis, **kwargs) 메서드

### Chapter 5. 탐색적 데이터 분석
1. df.isin(values) 메서드
2. ser.str 속성 → extract(), replace(), split(pat, expand), contains() 메서드 등
3. df.pipe(func) 메서드
4. pd.cut(x, bins, labels), pd.qcut(x, q, labels) 함수
5. ser.clip(lower, upper) 메서드
6. ser.cov(ser), ser.corr(ser, method) 메서드
7. 범주를 줄이기 위한 generalize() 함수 작성
8. df.unstack(level, fill_value) 메서드
9. pd.crosstab(index, columns, dropna, normalize) 함수

### Chapter 6. 데이터의 부분집합 선택
1. Index.get_loc(key), Index.get_loc(target, method) 메서드
2. Index.is_monotonic_increasing(), Index.is_monotonic_decreasing() 메서드

### Chapter 7. 행 필터링
1. pandas Boolean Indexing에서는 &, |, ~ 사용
2. iloc 연산자에서 Boolean Array를 활용하려면 to_numpy() 메서드 이용 필요
3. df.set_index(keys, drop), df.reset_index(level, drop, col_level, name) 메서드
4. ser.between(left, right, inclusive) 메서드
5. df.query(expr) 메서드 → SQL WHERE 구문 활용 가능
6. df.where(cond, other), df.mask(cond, other) 메서드

### Chapter 8. 인덱스 정렬
1. 인덱스의 정렬과 카티션 곱의 개념
2. pd.to_numeric(arg, errors) 함수
3. df.idxmax/idxmin(skipna, axis, numeric_only) 메서드

### Chapter 9. 그룹화를 위한 집계, 필터링, 변환
1. df.groupby(by, as_index, observed, dropna) 메서드
2. GroupBy.agg(func, *args, **kwargs) 메서드
3. pd.NamedAgg(column, aggfunc) 함수
4. Index.get_level_values(level) 메서드
5. Index.to_flat_index() 메서드 → 활용하여 flatten_cols 함수 제작 가능
6. GroupBy.ngroups, GroupBy.groups 속성, GroupBy.get_group(name), GroupBy.nth(n) 메서드
7. GroupBy.filter(func, dropna, *args, **kwargs) 메서드
8. GroupBy.transform(func, *args, **kwargs) 메서드
9. df.pivot(index, columns, values) 메서드
10. GroupBy.apply(func, *args, **kwargs) 메서드
11. np.sort(array, kind, axis) 함수
12. df.diff(periods, axis) 메서드
13. df.ffill/bfill() 메서드 → df.fillna() 메서드의 method 파라미터 이용
14. df.shift(periods, freq, fill_value) 메서드

### Chapter 10. 정돈된 형식으로 데이터 재구성
1. df.stack(level, dropna), df.unstack(level, fill_value) 메서드
2. df.melt(id_vars, value_vars, var_name, value_name) 메서드
3. pd.wide_to_long(df, stubnames, i, j, sep, suffix) 함수
4. df.pivot(index, columns, values) 메서드
5. df.pivot_table(index, columns, values, aggfunc, fill_value, margins) 메서드
6. df.swaplevel(i, j, axis) 메서드
7. df.rename_axis(mapper, axis) 메서드

### Chapter 11. pandas 객체 병합
1. pd.concat(objs, join, keys, names, ignore_index) 함수
2. df.join(other, on, how, lsuffix, rsuffix) 메서드
3. df.merge(right, how, on, left_index, right_index, suffixes) 메서드
4. df.add_suffix(suffix), df.add_prefix(prefix) 메서드
5. df.set_axis(label, axis) 메서드
6. glob.glob() 함수 → Path 모듈의 glob() 메서드로 대체

### Chapter 12. 시계열 분석
1. pd.to_datetime(arg, errors, unit, origin) 함수
2. pd.to_timedelta(arg, unit, errors) 함수
3. Timestamp.ceil/round/floor(freq), Timedelta.ceil/round/floor(freq) 메서드
4. Timestamp.year/month/day/hour/minute/second 속성
5. Timestamp.dayofweek/dayofyear/daysinmonth 속성, Timestamp.day_name() 메서드
6. Timedelta.components 속성, Timedelta.total_seconds() 메서드
7. pd.read_hdf(path or buf, key) 함수
8. pd.Interval(left, right, closed) 함수
9. pd.date_range(start, end, periods, freq) 함수
10. df.between_time(start_time, end_time, inclusive), df.at_time(time) 메서드
11. df.first('5D'/'5B'/'7W'/'3QS'/'A') 메서드
12. pd.DateOffset(n, normalize, **kwds) 함수
13. df.resample(rule, on) == df.groupby(pd.Grouper(freq, key)) 메서드
14. ser.dt 속성

### Chapter 13. pandas, matplotlib, seaborn을 이용한 시각화1
1. plt.subplots(nrows, ncols, sharex, sharey, subplot_kw) 함수
2. np.matrix.ravel() 메서드
3. ax.set_xlim/ylim(left, right), ax.set_xlabel/ylabel(xlabel, fontdict, loc, **kwargs) 메서드
4. ax.set_title(label, fontdict, loc, **kwargs),  fig.suptitle(t, x, y, **kwargs) 메서드
5. fig.get_size_inches(), fig.set_size_inches(w, h) 메서드
6. fig/ax.set_facecolor(color) 메서드
7. ax.spines 속성 → set_linewidth(linewidth), set_visible(b) 메서드 등
8. ax.set_xticks/yticks(ticks, labels, **kwargs) 메서드
9. ax.set_xticklabels/yticklabels(labels, fontdict, **kwargs) 메서드
10. ax.tick_params(axis, colors, which, direction, labelsize) 메서드
11. ax.stackplot(x, y, labels, colors, **kwargs) 메서드



### 2022년 7월 30일
1. Chapter 1 Pandas 기초 관련 복습 진행
2. Chapter 2 기본 DataFrame 연산 관련 복습 진행
3. Chapter 3 DataFrame 생성과 유지 관련 복습 진행
4. Chapter 4 데이터 분석 시작 관련 복습 진행

### 2022년 7월 31일
1. Chapter 5 탐색적 데이터 분석 관련 복습 진행
2. Chapter 6 데이터의 부분 집합 선택 관련 복습 진행
3. Chapter 7 행 필터링 관련 복습 진행
4. Chapter 8 인덱스 정렬 관련 복습 진행

### 2022년 8월 1일
1. Chapter 9 그룹화를 위한 집계, 필터링, 변환 관련 복습 진행(~ing)

### 2022년 8월 2일
1. Chapter 9 그룹화를 위한 집계, 필터링, 변환 관련 복습 진행
2. Chapter 10 정돈된 형식으로 데이터 재구성 관련 복습 진행(~ing)

### 2022년 8월 3일
1. Chapter 10 정돈된 형식으로 데이터 재구성 관련 복습 진행(~ing)

### 2022년 8월 4일
1. Chapter 10 정돈된 형식으로 데이터 재구성 관련 복습 진행
2. Chapter 11 Pandas 객체 병합 관련 복습 진행(~ing)

### 2022년 8월 5일
1. Chapter 11 Pandas 객체 병합 관련 복습 진행
2. Chapter 12 시계열 분석 관련 복습 진행(~ing)

### 2022년 8월 6일
1. Chapter 12 시계열 분석 관련 복습 진행
2. Chapter 13 matplotlib, seaborn을 이용한 시각화 복습 진행(~ing)

### 2022년 8월 7일
1. Chapter 13 matplotlib, seaborn을 이용한 시각화 복습 진행
2. Chapter 14 Pandas 디버깅과 테스트 일부 관련 복습 진행